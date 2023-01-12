<template>
    <div class="container">
        <CardElement v-for="CardElement in store.YuGiOhList"
            :imgUrl="CardElement.card_images[0].image_url"
            :name="CardElement.name"
            :archetype="CardElement.archetype"
            :type="CardElement.type"
            :race="CardElement.race"
            :effect="CardElement.desc"
            :price="CardElement.card_prices"/>
    </div>
</template>

<script>
    import CardElement from './CardElement.vue';

//store.js
import { store } from '../store.js';

export default {
    components: {
        CardElement,
    },
    data(){
        return{
            store
        }
    },
    created(){
    }
}
</script>

<style lang="scss" scoped>
    .container{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        background-color: white;
        padding: 60px 100px;
    }
</style>