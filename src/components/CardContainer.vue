<template>
    <div class="container">
        <CardElement v-for="CardElement in store.YuGiOhList"/>
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
        background-color: white;
        padding: 60px 100px;
    }
</style>