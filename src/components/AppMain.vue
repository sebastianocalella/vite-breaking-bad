<template>
    <div class="container">
        <CardContainer />
    </div>
</template>

<script>
//components
import CardContainer from './CardContainer.vue';

//store.js
import { store } from '../store.js';

import axios from 'axios';

export default {
    components: {
        CardContainer,
    },
    data() {
        return {
            store
        }
    },
    methods: {
        getYuGiOhList() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0', {
                params: {
                }
            })
                .then((response) => {
                    this.store.YuGiOhList = response.data.data;
                    console.log(this.store.YuGiOhList)
                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },
    created() {
        this.getYuGiOhList();
    }
}
</script>

<style lang="scss" scoped>
div.container {
    padding: 60px 100px;
}
</style>