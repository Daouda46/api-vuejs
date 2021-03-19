<template>
  <div id="app">
   
    <!-- <header-tp></header-tp>
  <router-view></router-view> -->
  <meteo></meteo>
  </div>
</template>

<script>
  import Meteo from './components/Meteo.vue'
  // import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    // 'header-tp':Header,
    'meteo':Meteo,
    
  }
}
</script>

<style>
  body{
    background: #43c6ac;
    background: linear-gradient(to right, #f8ffae, #43c6ac);
  }
</style>
