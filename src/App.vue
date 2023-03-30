<script>
  import axios from 'axios';
  import { store } from './store.js';

  import MyHeader from './components/MyHeader.vue';
  import SelectBar from './components/SelectBar.vue';
  import MyMain from './components/MyMain.vue';

  export default {
    components: {
      MyHeader,
      SelectBar,
      MyMain
    },
      data() {
        return {
          store
      }
    },
    methods: {
      getArchetypesList() {
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(response =>{
          this.store.archetypesList = response.data;
        });
      },
      getCardList() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0')
        .then(response => {
          this.store.cardList = response.data.data;
        });
      },
      filterCards(){
        let urlApi = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0';
        if(this.store.option == ''){
          this.getCardList();
        }else{
          urlApi += `&archetype=${this.store.option}`
          axios.get(urlApi)
          .then(response => {
          this.store.cardList = response.data.data;
        });
        }
      }
    },
    created() {
      this.getCardList();
      this.getArchetypesList();
    }
  }
</script>



<template>
  <MyHeader/>
  <SelectBar @filterCards="filterCards"/>
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