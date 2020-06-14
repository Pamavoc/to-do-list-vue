<template>
  <div id="app">
    <header-top></header-top>
    <contenu></contenu>
  </div>
</template>

<script>
import Contenu from './components/Contenu.vue'
import Header from './components/Header/Header.vue'


export default {
  name: 'App',
  components: {
   
   'contenu': Contenu,
   'header-top': Header
    
  }

}
</script>

<style>

</style>
