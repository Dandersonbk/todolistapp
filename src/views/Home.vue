<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    
  </div>
</template>

<script>
import AddTodo from '../components/AddTodo';
import Todos from '../components/Todos';
//import axios from 'axios';

export default {
  name: 'Home',
  components: {
    AddTodo,
    Todos
  },
  data(){
    return {
      todos: [
        {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
  },
  {
    "userId": 1,
    "id": 2,
    "title": "quis ut nam facilis et officia qui",
    "completed": false
  },
  {
    "userId": 1,
    "id": 3,
    "title": "fugiat veniam minus",
    "completed": false
  },
  {
    "userId": 1,
    "id": 4,
    "title": "et porro tempora",
    "completed": true
  },
  {
    "userId": 1,
    "id": 5,
    "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
    "completed": false
  },
      ]
    }
  },
  methods:{
    deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      this.todos =[...this.todos, newTodo];
    }
        }
  
}
</script>

<style>
*{
box-sizing:border-box;
margin: 0;
padding:0;

}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  background-color: #b2dfdb;
}

</style>

