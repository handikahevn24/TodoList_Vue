<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/layouts/Header'; //import Komponen Header
import Todos from './components/Todos'; //import Komponen Header
import AddTodo from './components/AddTodo'; //import Komponen Header

export default {
  name: 'app',
  components: {
    Header, //Componen Header hasil import
    Todos, //Componen Todos hasil import
    AddTodo //Componen AddTodo hasil import
  },
  data(){
    return {
      todos: [ //dummy data todo awal
        {
          id: 1,
          title: "Percobaan 1",
          completed: false
        },
        {
          id: 2,
          title: "Percobaan 2",
          completed: false
        },
        {
          id: 3,
          title: "Percobaan 3",
          completed: false
        },
      ] //todos
    }
  },
  methods: {
    deleteTodo(id){ //method untuk hapus Todo
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){ //method untuk tambah Todo
      this.todos = [...this.todos, newTodo];
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
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #666;
}
</style>
