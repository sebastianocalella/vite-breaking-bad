<template lang="">
    <div class="container">
        <label for="archetype-select">choose an Archetype:</label>
        <select 
            v-model="selectedArchetype" 
            @change="$emit('archetypeFilter',selectedArchetype)"
            name="archetypes" 
            id="archetype-select">
            <option v-for="(archetype,index) in archetypeList" :value="archetype">{{archetype}}</option>
        </select>
    </div>
</template>

<script>

export default {
    data(){
        return{
            archetypeList:['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
            selectedArchetype: null
            
        }
    }
}

</script>

<style lang="scss" scoped>
    label{
        font-size: 2rem;
        margin-right: 20px;
    }
    select{
        width: 200px;
        height: 40px;
        font-size: 1.6rem;
    }
</style>