<template>
    <h2>{{ name }}</h2>
    <p>{{ description }}</p>
    <img :src="imgSrc" alt="post's photo">
</template>

<script>
export default {
    props: {
        name: String,
        description: String,
        imgSrc: String
    }
}
</script>