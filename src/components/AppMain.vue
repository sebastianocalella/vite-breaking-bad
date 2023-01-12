<template>
    <div class="container">
        <ArchetypesFilter />
        <CardContainer />
    </div>
</template>

<script>

//store.js
import { store } from '../store.js';

import axios from 'axios';

//components
import ArchetypesFilter from './ArchetypesFilter.vue';
import CardContainer from './CardContainer.vue';

export default {
    components: {
        CardContainer,
        ArchetypesFilter
    },
    data() {
        return {
            store
        }
    },
    methods: {
        getYuGiOhList() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
                params: {
                    num: 10,
                    offset: 0
                }
            })
                .then((response) => {
                    this.store.YuGiOhList = response.data.data;
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