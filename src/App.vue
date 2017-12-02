<template>
  <div id="app">
    <meu-menu sistema='dominio'></meu-menu>
    <img src="./assets/logo.png">    
    <img src="./assets/logo_duxus.png">
    <h1>{{ msg }}</h1>    
  </div>
</template>

<script>

import Menu from './components/menu/menu.vue';

export default {

  components: {
    'meu-menu' : Menu
  },

  data () {
    return {
      msg: 'Esqueletinho de VueJS para a Duxus'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
