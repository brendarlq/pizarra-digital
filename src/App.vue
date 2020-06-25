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
              <section class="nes-container with-title">
                <h3 class="title">And the winner is...</h3>
                <i class="nes-icon trophy is-large"></i>
              </section>
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
          position: false,
          pokemon: "nes-bulbasaur"
        },
        {
          id: 2,
          title: "Do laundry",
          autor: "Via",
          position: true,
          pokemon: "nes-kirby"
        },
        {
          id: 3,
          title: "Cook food",
          autor: "Laura",
          position: false,
          pokemon: "nes-squirtle"
        },
        {
          id: 4,
          title: "Clean up room",
          autor: "Andrea",
          position: true,
          pokemon: "nes-mario"
        },
        {
          i: 5,
          title: "Finish work",
          autor: "Brenda",
          position: false,
          pokemon: "nes-charmander"
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
  font-size: 12px !important;
}
.col-xs-6 {
  flex-basis: 50%;
}
</style>