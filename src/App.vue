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
    let emailLista = []
    axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
    .then(function(response){
      const email = response.data
      for (let x = 0; x < 10; x++) {
        emailLista.push(email.response)
      }

  

      console.log(emailLista)
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
