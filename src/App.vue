<script>
  import axios from 'axios';
  import { store } from './store.js';
  import MyMain from './components/MyMain.vue';

  export default {
    components: {
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

</template>


<style lang="scss">
  @use './styles/general.scss';

</style>