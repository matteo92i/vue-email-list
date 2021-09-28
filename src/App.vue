<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  components: {
    
  },
  data: function (){
    return{
      emailLista: [],
    }
  },
  mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
    .then(function(response){
      const email = response.data
      console.log(email.response)
    })
  }
    
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
