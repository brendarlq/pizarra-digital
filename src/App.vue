<template>
  <div id="app">
    <div class="nes-container with-title">
      <p class="title">Pizarra Digital</p>
      <div class="container" style="margin-bottom: 30px;">
        <div class="row">
          <div class="col-xs">
            <div class="box">
              <AddTodo v-on:add-todo="addTodo" />
              <br />
              <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
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
import AddTodo from "./components/AddTodo";
export default {
  name: "app",
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Go workout",
          autor: "Monse",
          completed: false,
          pokemon: "nes-bulbasaur"
        },
        {
          id: 2,
          title: "Do laundry",
          autor: "Via",
          completed: true,
          pokemon: "nes-kirby"
        },
        {
          id: 3,
          title: "Cook food",
          autor: "Laura",
          completed: false,
          pokemon: "nes-squirtle"
        },
        {
          id: 4,
          title: "Clean up room",
          autor: "Andrea",
          completed: true,
          pokemon: "nes-mario"
        },
        {
          i: 5,
          title: "Finish work",
          autor: "Brenda",
          completed: false,
          pokemon:"nes-charmander"
        }
      ]
    };
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
};
</script>
<style>
#app {
  font-size: 14px !important;
}
</style>