<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Showtodos v-bind:todosDataProps="todosData" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Showtodos from './components/showtodos.vue'
import Header from './components/layout/header.vue'
import AddTodo from './components/AddTodo.vue'

export default {
  name: 'App',
  components: {
     Header,
    Showtodos,
    AddTodo
  },
  data() {
    return {
     todosData: [
       {
         id: 1,
         title: "Todo  One",
         completed: false
       },
        {
         id: 2,
         title: "Todo  two",

         completed: true,
       },
        {
         id: 3,
         title: "Todo  Three",
         completed: false
       }
     ]  
    }
  },
  methods: {
    deleteTodo(id) {
       this.todosData = this.todosData.filter(todosData => todosData.id !== id);
    },
    addTodo(newTodo) {
      this.todosData = [...this.todosData, newTodo]
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #ffff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }

</style>
