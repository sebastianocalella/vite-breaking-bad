<template>
    <div class="container">
        <CardElement />
    </div>
</template>

<script>
    import CardElement from './CardElement.vue'

export default {
    components: {
        CardElement,
    } 
}
</script>

<style lang="scss" scoped>
    .container{
        background-color: white;
        padding: 60px 100px;
    }
</style>