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
          autor: "monse",
          completed: false
        },
        {
          id: 2,
          title: "Do laundry",
          autor: "Via",
          completed: true
        },
        {
          id: 3,
          title: "Cook food",
          autor: "laura",
          completed: false
        },
        {
          id: 4,
          title: "Clean up room",
          autor: "andrea",
          completed: true
        },
        {
          i: 5,
          title: "Finish work",
          autor: "brenda",
          completed: false
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