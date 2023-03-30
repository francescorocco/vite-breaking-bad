<script>
    import {store} from '../store.js';
    export default{
        name: "SelectBar",

        data() {
            return {
                store
            }
        },
    }
</script>


<template>
    <div>
        <select v-model="store.option" @change="$emit('filterCards')">
            <option value="" >All</option>
            <option :value="element.archetype_name" v-for="(element, index) in store.archetypesList" :key="index">{{ element.archetype_name }}</option>
        </select>
    </div>
</template>


<style scoped lang="scss">
    select {
        font-size: 20px;
        text-align: center;
        border: 5px solid rgb(212, 143, 56);
        border-radius: 20px;
        background-color: rgb(9, 147, 130);
        font-weight: 700;
        margin-bottom: 30px;
    }

    option{
        font-weight: 700;
        font-size: 20px;
    }

    div{
        text-align: center;
    }
</style>