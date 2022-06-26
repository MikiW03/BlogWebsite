<template>
    <div class="post">
        <h2>{{ title }}</h2>
        <p>{{ body }}</p>
        <ul class="tags">
            <li v-for="(tag, i) in tags" :key="i">
                {{ tag }}
            </li>
        </ul>
        <p class="reactions">
            <img class="like-icon" src="https://i.pinimg.com/originals/39/44/6c/39446caa52f53369b92bc97253d2b2f1.png"
                alt="like-icon">
            {{ reactions }}
        </p>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        body: String,
        tags: Array,
        reactions: Number
    }
}
</script>

<style>
.post {
    background-color: var(--clr-primary);
    border-radius: .2em;
    padding: 1em 1em;
    margin-block: 1em;
}

.post>.tags {
    display: flex;
    flex-wrap: wrap;
    gap: 1em;
    padding: 0;
    list-style-type: none;
    margin-block: 1em;
    margin-inline: 0;
}

.post>.tags>li {
    padding: .1em .5em;
    border-radius: .2em;
    background: var(--clr-accent);
}

.post>.reactions {
    display: flex;
    gap: .2em;
    align-items: center;
    height: 30px;
}

.post>.reactions>img {
    max-height: 100%;
}
</style>