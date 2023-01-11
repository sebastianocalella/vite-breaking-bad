<template>
    <div class="card">
        <img :src="imgUrl" alt="">
        <h2>{{ name }}</h2>
        <p>{{ archetype }}</p>
    </div>
</template>

<script>

export default {
    props:{
        imgUrl: String,
        name: String,
        archetype: String
    }
}
</script>

<style lang="scss" scoped>

    @use '../styles/partials/variables' as *;
    .card{
        width: 421px;
        background-color: $main-color;
        margin-bottom: 20px;
        padding-bottom: 2rem;

        h2{
            color: white;
            text-align: center;
            text-transform: uppercase;
            padding: 2rem 0;
        }

        p{
            font-size: 2rem;
            text-align: center;
        }
    }
</style>