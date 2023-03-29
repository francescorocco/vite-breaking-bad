<script>
  import axios from 'axios';
  import { store } from './store.js';

  import MyHeader from './components/MyHeader.vue';
  import MyMain from './components/MyMain.vue';

  export default {
    components: {
      MyHeader,
      MyMain
    },
      data() {
        return {
          store
      }
    },
    methods: {
      getCardList() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?staple=yes')
        .then(response => {
          this.store.cardList = response.data.data;
          console.log(this.store);
        });
      }
    },
    created() {
      this.getCardList();
    }
  }
</script>



<template>
  <MyHeader/>
  <MyMain/>
</template>


<style lang="scss">
  @use './styles/general.scss';

  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
</style>