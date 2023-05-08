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
  created() {
    this.callArchetype(),
    this.saveArchetype()
  },
  
  computed: {
  },
  methods: {
    //Funzione iniziale per richiamare gli archetipi
    callArchetype() {
      axios.get( 'https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then( (res) => {
          console.log(res.data) //array personaggi yu-gi-oh
        
          const infoApi = res.data;
          store.arrayArchetype = infoApi;
      })
    },

    //Funzione per mostrare l'archetipo selezionato
    saveArchetype() {
      axios.get( `https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.inputArchetype}`)
        .then( (res) => {
          console.log(res.data.data) //array personaggi yu-gi-oh
        
          const infoArchetype = res.data.data;
          store.arrayPersonaggi = infoArchetype;
      })
      
    },

  }
  
}

</script>

<template>

  <HeaderComp :titoloProps = " 'Yu-Gi-Oh!' " :classiProps="'text-center'" />

  <main>

    <SearchComp @selezionaArchetipo="saveArchetype()"/>
    
    <PersonaggiComp/>

  </main>

</template>

<style lang="scss">
@use './style/main.scss';

  main {
    background-color: rgb(212,143,56);
    min-height: calc(100vh - 70px);
  }
</style>
