<template>
  <div id="app">
    <Init moedaA="BRL" moedaB="USD" />
  </div>
</template>

<script>
import Init from './components/Conversor.vue'
//import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      nome: 'Richard'
    }
  },
  components: {
    Init
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
