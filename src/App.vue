<template>
  <div id="app">
    <v-header></v-header>
    <v-middle></v-middle>
    <v-rolldata></v-rolldata>
    <v-foot></v-foot>
  </div>
</template>

<script>
import header from './components/Header'
import middle from './components/Middle'
import rolldata from './components/RollData'
import foot from './components/Foot'
export default {
  name: 'App',
  components: {
    'v-header': header,
    'v-middle': middle,
    'v-rolldata': rolldata,
    'v-foot': foot
  }
}
</script>

<style>
/*#app {*/
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
/*}*/
*{
  padding: 0;
  margin: 0;
}
  html{
    font-size: 13.333vw;
  }
</style>
