<template>
  <div id="app">
    <img alt="Boolean Logo" src="./assets/img/logo-small.png">
    <HelloWorld msg="Benvenuto nel generatore casuale di mail by Boolean Api" :mailRandom='mailRandom'/>
    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: function(){
    return{
      mailRandom: '',
    }
  },
  mounted(){
    const result=[];
    let self=this;
    for(let i= 0 ; i<10; i++){
    axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
    .then((response)=>{
      
      
         result.push(response.data.response);
        
      })
      
    }
    self.mailRandom = result;
  }
}
</script>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  img{
    width: 200px;
    transition: 1s cubic-bezier(0.19, 1, 0.22, 1);
    &:hover{
          transform: scale(0.8);
    }
  }
  
}
</style>
