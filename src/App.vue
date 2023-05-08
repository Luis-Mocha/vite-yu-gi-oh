<script>
//axios viene importato automaticamente
import axios from 'axios';
import {store} from './store'
import HeaderComp from './components/HeaderComp.vue';
import PersonaggiComp from './components/PersonaggiComp.vue';
import SearchComp from './components/SearchComp.vue';

export default {
  name: 'app',
  components: {
    HeaderComp,
    PersonaggiComp,
    SearchComp,
  },
  data() {
    return {
      store
    }
  },
  // created () {
  //   this.callApi()
  // },
  computed: {
    //funzione Call Api
      callApi() {
        if (store.testoRicerca !== '') {
          axios.get( `https://db.ygoprodeck.com/api/v7/cardinfo.php?name=${store.testoRicerca}`)
          .then( (res) => {
          console.log(res.data.data) //array personaggi yu-gi-oh
        
          const infoApi = res.data.data;
          store.arrayPersonaggi = infoApi;
        })
        } else {
          axios.get( 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=24&offset=0')
          .then( (res) => {
            console.log(res.data.data) //array personaggi yu-gi-oh
          
            const infoApi = res.data.data;
            store.arrayPersonaggi = infoApi;
          })
        }
      }
    // Fine Call Api
  },
  // methods: {
  //   //funzione Call Api
  //      callApi() {
  //        if (store.testoRicerca !== '') {
  //          axios.get( `https:db.ygoprodeck.com/api/v7/cardinfo.php?num=${store.testoRicerca}&offset=0`)
  //          .then( (res) => {
  //          console.log(res.data.data) //array personaggi yu-gi-oh
        
  //          const infoApi = res.data.data;
  //          store.arrayPersonaggi = infoApi;
  //        })
  //        } else {
  //          axios.get( 'https:db.ygoprodeck.com/api/v7/cardinfo.php?num=24&offset=0')
  //          .then( (res) => {
  //            console.log(res.data.data) //array personaggi yu-gi-oh
          
  //            const infoApi = res.data.data;
  //            store.arrayPersonaggi = infoApi;
  //          })
  //        }
  //      }
  //   //Fine Call Api
  // }
}

</script>

<template>

  <HeaderComp :titoloProps = " 'Yu-Gi-Oh!' " :classiProps="'text-center text-danger'" />

  <main>

    <SearchComp @nomeEmit="callApi()"/>
    
    <PersonaggiComp/>

  </main>

</template>

<style lang="scss">
@use './style/main.scss';

  main {
    background-color: rgb(212,143,56);
  }
</style>
