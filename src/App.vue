<template>
  <div id="app">
    <div class="nes-container with-title">
      <p class="title">
        <i class="nes-icon star"></i>
        <i class="nes-icon star"></i> Pizarra Digital
        <i class="nes-icon star"></i>
        <i class="nes-icon star"></i>
      </p>
      <div>
        <div class="row">
          <div class="col-xs">
            <div class="box">
              <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
            </div>
          </div>
          <div class="col-xs-offset col-xs-4">
            <div class="box">
              <AddTodo v-on:add-todo="addTodo" />
              <br />
              <MostVoted v-bind:mostVoted="findMostVoted(todos)" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "nes.css/css/nes.min.css";
import Todos from "./components/Todos";
import MostVoted from "./components/MostVoted";
import AddTodo from "./components/AddTodo";
export default {
  name: "app",
  components: {
    Todos,
    AddTodo,
    MostVoted
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Go workout",
          autor: "Monse",
          position: false,
          picture: "monse.jpg",
          cont: 1
        },
        {
          id: 2,
          title: "Do laundry",
          autor: "Via",
          position: true,
          picture: "via.jpg",
          cont: 1
        },
        {
          i: 6,
          title: "Finish work",
          autor: "Pedro",
          position: false,
          picture: "pedro.jpg",
          cont: 1
        },
        {
          id: 3,
          title: "Cook food",
          autor: "Laura",
          position: true,
          picture: "laura.jpg",
          cont: 1
        },
        {
          id: 4,
          title: "Clean up room",
          autor: "Andrea",
          position: false,
          picture: "andrea.jpg",
          cont: 3
        },
        {
          i: 7,
          title: "Finish work",
          autor: "Saúl",
          position: true,
          picture: "saul.jpg",
          cont: 1
        },
        {
          i: 5,
          title: "Finish work",
          autor: "Brenda",
          position: false,
          picture: "brenda.jpg",
          cont: 1
        }
      ],
    };
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    },
    findMostVoted() {
      let sortedTodos = [...this.todos];
      sortedTodos = sortedTodos.sort((a, b) => b.cont - a.cont);
      return sortedTodos[0];
    }
  }
};
</script>
<style>
#app {
  font-size: 12px !important;
}
</style>