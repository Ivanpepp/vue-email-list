<template>
  <div v-if="mailRandom.length == 10 " class="hello">
    <h1>{{ msg }}</h1>
    <div  class="list-container">
       <ul>
        <li v-for="(element,index) in mailRandom" :key="index">
        {{element}}
        </li>
      </ul>
    </div>
     
    
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    mailRandom: Array
  },
}
</script>


<style scoped lang="scss">
h1{
  padding: 20px;
}
.list-container{
  display: flex;
  justify-content: center;
  min-width: 800px;
  ul{
    list-style: none;
    margin: 50px;
    font-size: 1.5rem;
    font-weight: bold;
    width: 50%;
    border: 2px solid black;
    
    li{
      border-bottom: 1px solid rgb(170, 170, 170);
      line-height: 50px;
      
    }
}
  
    
  }
</style>
