<template>
<main>

    <input type="text" class="new-todo" placeholder="ajoutez une taches" v-model="newTodo" @keyup.enter="addTodo">
    <ul class="todo-list">
        <li class="todo" v-for="(todo,i) in filteredTodo" :key="i" :class="{success: todo.completed}">
          <div class="views">
              <label for="">{{ todo.name }}</label>
              <input type="checkbox" v-model="todo.completed">
              
         </div>
        </li>
    </ul>
    <section>
        <span class="todo-count"><strong>{{ remaining }}</strong> Tache à faire </span>
        <ul class="filter">
            <li><a href="#" :class="{selected: filter === 'all'}" @click.prevent="filter = 'all'">Toutes</a></li>
            <li><a href="#" :class="{selected: filter === 'todo'}"  @click.prevent="filter = 'todo'">A faires</a></li>
            <li><a href="#" :class="{selected: filter === 'done'}"  @click.prevent="filter = 'done'">Faites</a></li>
        </ul>
    </section>
    

</main>
</template>

<script>
export default {
  name: 'Todo',
  data() {
      return {
          todos: [{
             name: "Aller faire les courses",
             completed: false
          }],
          newTodo: '',
          filter: 'all'
      }
  },
  methods: {
      addTodo (){
          this.todos.push({
              completed: false,
              name: this.newTodo
          })
          this.newTodo = ''
      }
  },
  computed: {
      remaining () {
        return this.todos.filter(todo => !todo.completed).length
      },
      filteredTodo() {
          if(this.filter === 'todo'){
              return this.todos(todo => !todo.completed)
          }else if(this.filter === 'done') {
              return this.todos(todo => todo.completed)
          }
             return this.todos;
          

      }
  }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

input{
    padding: 10px;
    border: 2px solid silver;
    border-radius: 10px;
}
.success {
   background-color: #a2d17a ;
}
.danger {
    background-color: #e46c73;
}
li {
    color: white;
    list-style: none;
    background-color: #e46c73;
    padding: 10px;
    border: 1px solid white;
    border-radius: 10px;
    margin-bottom: 10px;
}

.views {
    display: flex;
    justify-content: space-between;

    
}

.filter {
    display: flex;
    justify-content: space-between;
    
}
.filter li {
    background: #59BFCB;
    
}
.filter a {
    text-decoration: none;
    color: #FFF;
    
}


</style>
