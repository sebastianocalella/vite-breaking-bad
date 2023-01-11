<template>
    <div class="card">
        <img :src="imgUrl" alt="">
    </div>
</template>

<script>

export default {
    props:{
        imgUrl: String
    }
}
</script>

<style lang="scss" scoped>

    @use '../styles/partials/variables' as *;
    .card{
        height: 420px;
        width: 280px;
        background-color: $main-color;
        padding: 20px;
        margin-bottom: 20px;
    }
</style>