<script>
//axios viene importato automaticamente
import axios from 'axios';
import {store} from './store'
import HeaderComp from './components/HeaderComp.vue';
import PersonaggiComp from './components/PersonaggiComp.vue';

export default {
  name: 'app',
  components: {
    HeaderComp,
    PersonaggiComp,
  },
  data() {
    return {
      store
    }
  },
  created () {
    this.callApi()
  },
  methods: {
    callApi() {
      axios.get( 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=12&offset=0')
      .then( (res) => {
        console.log(res.data.data) //array personaggi yu-gi-oh
        
        const infoApi = res.data.data;
        store.arrayPersonaggi = infoApi;
      })
    },
  }

}

</script>

<template>

  <HeaderComp :titoloProps = " 'Yu-Gi-Oh!' " :classiProps="'text-center text-danger'" />

  <main>
    
    <PersonaggiComp/>

  </main>

</template>

<style lang="scss">
@use './style/main.scss';

  main {
    background-color: rgb(212,143,56);
  }
</style>
