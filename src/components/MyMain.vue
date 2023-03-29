<script>
    import CardList from './CardList.vue';
    export default {
        name: "MyMain",
        components:{
            CardList
        }

        
    }
</script>


<template>

    <main class="p-5">
        <CardList/>
    </main>

</template>


<style scoped lang="scss"> 
    main{
        background-color: rgb(212, 143, 56);
    }
</style>