<template>
  <div id="app">
    <div class="header">
      <h1>Taches à réaliser</h1>
       <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ea hic quidem cum maxime sunt doloribus excepturi necessitatibus, aspernatur nihil id, rem inventore, a veritatis iste sed sint nam tempore architecto?
      </p>
    </div>
    
    <Todo />

    <div class="footer">
      <h4>Fait par Rachid B with Vuejs</h4>
    </div>

   
  </div>
</template>

<script>

import Todo from './components/Todo.vue'

export default {
  name: 'App',
  components: {
    Todo
  }
}
</script>

<style>
body {
  background-color: #232323;
}
#app {
  font-family: Poppins;
  border: 2px solid #232323;
 background: -webkit-linear-gradient(left, #e46c73, #cb66ae, #59BFCB, #a2d17a);
 color: black;
border-radius: 20px;
}
.header, .footer {
  padding: 10px;
  text-align: center;
  color: aliceblue;
}


</style>
