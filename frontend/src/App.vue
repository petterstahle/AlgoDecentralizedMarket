<template>
  <div id="app">
    <AlgoDeMarket />
  </div>
</template>

<script>
import AlgoDeMarket from './components/AlgoDeMarket.vue'
export default {
  name: 'App',
  components: {
    AlgoDeMarket
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

body  {
  background-image: url("logo.png");
  background-color: #cccccc;
  background-position: center;
  background-repeat: no-repeat;

}
</style>
