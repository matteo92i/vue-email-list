<template>
  <div id="app">
    <Listaemail/>
    <ul>
      <li>{{emailLista}}</li>
    </ul>

    
  </div>
</template>

<script>
import Listaemail from './components/Listaemail.vue';
import axios from 'axios';


export default {
  name: 'App',
  components: {
    Listaemail
    
  },
  data: function (){
    return{
      emailLista: []
    }
  },
  mounted(){
    

    for(let i = 0; i < 10; i++){
    axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
    .then((response)=>{
    const email = response.data.response
    this.emailLista.push(email)
    });
      
      
    }

      

  

      console.log(this.emailLista)

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
