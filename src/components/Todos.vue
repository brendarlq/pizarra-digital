<template>
  <div>
    <div class="nes-container with-title is-dark">
      <h3 class="title">Frases</h3>
        <div v-bind:key="todo.id" v-for="todo in todos">
          <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" />
        </div>
    </div>
  </div>
</template>

<script>
import Todo from "./Todo";
export default {
  name: "Todos",
  components: {
    Todo
  },
  props: ["todos"]
};
</script>

<style scoped>
</style>