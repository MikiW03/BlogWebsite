<template>
  <h1>Blog</h1>
  <div id="posts" v-if="!error">
    <PostItem v-for="post in posts" :key="post.id" v-bind="post" />
  </div>
  <p class="error" v-else>Sorry. No posts to display. <br> {{ error }} </p>
</template>

<script>
import PostItem from './components/PostItem.vue'

export default {
  components: {
    PostItem
  },
  created() {
    fetch("https://dummyjson.com/posts")
      .then(response => response.json())
      .then(data => {
        ({ posts: this.posts } = data)
      })
      .catch(error => {
        this.error = error
      })
  },
  data() {
    return {
      posts: {},
      error: ""
    }
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter&display=swap');

:root {
  --clr-primary: #1c1c1c;
  --clr-bg: #121212;
  --clr-font: #ffffff;
  --clr-accent: #5e91ff;
}

* {
  margin: 0;
}

body {
  margin: 0;
  background-color: var(--clr-bg);
  color: var(--clr-font);
  font-family: "Inter";
  line-height: 1.4;
}

#app {
  width: clamp(40vw, 500px, 90vw);
  margin-inline: auto;
  margin-block: 0;
}

.error {
  color: red;
}
</style>
