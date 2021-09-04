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
        axios.get('https://shouldideploy.today/api?tz=America/Sao_Paulo',
          {
            headers: {
              'Access-Control-Allow-Credentials': 'true',
              'Access-Control-Allow-Origin': '*',
              'Content-type': 'application/json',
              'Access-Control-Allow-Methods': 'GET,OPTIONS,PATCH,DELETE,POST,PUT',
              'Access-Control-Allow-Headers':
              'X-CSRF-Token, X-Requested-With, Accept, Accept-Version, Content-Length, Content-MD5, Content-Type, Date, X-Api-Version'
            }
          }
        )
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
