<template>
  <div id="app">
    <div id="nav">
     <Header />

    </div>
    <router-view/>
  </div>
</template>

<script>

import Header from './components/layout/Header';
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Header,
  },
  data(){
    return {
      todos: []
    }
  },
  methods : {
    deleteTodo(id){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      // eslint-disable-next-line
        .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => console.log(err));
      
    },
    addTodo(newTodo){
      const { title, completed } = newTodo; //this is destructuring

      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      })
      //the above gives us a promise so we do the below
      .then(res => this.todos =[...this.todos,  res.data])
      .catch(err => console.log(err));

    }
  },
  //making HTTP requests from json placeholder using axios library, limiting to 10, usually you build the backend API in Flask etc
  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
     .then( res => this.todos = res.data)
     .catch( err => console.log(err));


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
}


</style>
