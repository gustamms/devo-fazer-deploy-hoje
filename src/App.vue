<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Mensagem msg="teste"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Mensagem from './components/Mensagem.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Mensagem
  },
  created: function(){
      this.requestApi()
  },
  methods: {
      requestApi: function() {
        axios.post('http://shouldideploy.today/api?tz=America/Sao_Paulo')
        .then((response) =>{
          console.log(response);
        })
      }
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
  margin-top: 60px;
}
</style>
