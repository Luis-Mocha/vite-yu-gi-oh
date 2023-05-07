<script>
//axios viene importato automaticamente
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue';
import PersonaggiComp from './components/PersonaggiComp.vue';

export default {
  name: 'app',
  components: {
    HeaderComp,
    PersonaggiComp,
  },
  created () {
    axios.get( 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0')
      .then( (res) => {
        console.log(res.data.data)
      })
  }
}

</script>

<template>

  <HeaderComp :titoloProps = " 'Yu-Gi-Oh!' " :classiProps="'text-center text-danger'" />

  <main class="container">

    <PersonaggiComp/>

  </main>

</template>

<style lang="scss">
@use './style/main.scss';
</style>
