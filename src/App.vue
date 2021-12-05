<template>
<div id="app">
  <h1>{{title}}</h1>
  <todo-list v-if="todos.length"   :todos='todos' @del-this="deleteThis"></todo-list>
  <p v-else>No hay tareas</p>
  <add-todo @add-list='addTodo' ></add-todo>
  <br>
  <delete-todo @delete-all='deleteAll' ></delete-todo>
</div>
</template>

<script>
import AddTodo from './components/AddTodo.vue'
import DeleteTodo from './components/DeleteTodo.vue'
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    AddTodo,
    DeleteTodo
  },
  data() {
    return {
      title:'Lista de Tareas',
      todos: [
        { 
          id: 1,
          title: "Learn JavaScript", 
          done: false 
        }, { 
          id: 2,
          title: "Hola", 
          done: false 
        }, { 
          id: 3,
          title: "Que haces", 
          done: true 
        }, { 
          id: 4,
          title: "Build something awesome", 
          done: true 
        }
      ]      
    }
  },
    methods:{
    addTodo(name){
      this.todos.push({
        title:name,
        done:false
      })
      
    },
    deleteAll(){
      this.todos=[]
    },
    deleteThis(key){
      this.todos.splice(key,1)
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
  color: #000000;
  margin-top: 60px;
  text-align: left;
}
</style>
