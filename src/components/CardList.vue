<script>
    import {store} from '../store.js';
    import CardOfCard from './CardOfCard.vue';

    export default {
        name: 'CardList',
        data() {
            return {
                store
            }
        },
        components: {
            CardOfCard
        }
    }
</script>


<template>
    <div class="ms-container d-flex">
        <div class="card-wrapper" v-for="(card, index) in store.cardList" :key="index">
            <CardOfCard :image="card.card_images[0].image_url" :name="card.name" :race="card.race"/>
        </div>
    </div>
</template>



<style scoped lang="scss">
    .ms-container{
        flex-wrap: wrap;
        justify-content: center;
        background-color: white;
    }

    .card-wrapper{
        width: calc(100% / 5 - 50px);
        margin: 5px 5px;
        background-color: rgb(212, 143, 56);
    }
</style>