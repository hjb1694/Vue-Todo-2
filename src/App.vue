<template>
  <div id="main">
    <app-header/>
    <div class="container">
        <app-form :addToDo="addToDo"/>
        <app-list :items="todos" :toggleCompletion="completeToDo"/>
    </div>
  </div>
</template>


<script>
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import List from './components/List.vue';

export default {
  components : {
    'app-header' : Header, 
    'app-form' : Form, 
    'app-list' : List
  }, 
  data : function(){
    return {
      todos : []
    }
  }, 
  methods : {
    addToDo : function(newItem){

      const addedItem = {
        id : Date.now(),
        task : newItem,
        completed : false
      }
      
      this.todos = [...this.todos, addedItem]

    }, 
    completeToDo : function(id){

       let index = this.todos.findIndex(item => item.id == id);

       this.todos[index].completed = !this.todos[index].completed

    }
  }

}
</script>


<style>

  @import url('https://fonts.googleapis.com/css?family=Open+Sans&display=swap');

  *,*::before,*::after{
    margin:0;
    padding:0;
    box-sizing:inherit;
  }
  html{
    box-sizing:border-box;
    font-size:62.5%;
  }
  body{
    background:#edf8ff;
    font-family: 'Open Sans', sans-serif;
  }

  .container{
    width:50%;
    margin:2rem auto;
  }
</style>