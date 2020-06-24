<template>
  <div class="row">
    <div v-if="todo.completed">
      <i v-bind:class="todo.pokemon"></i>
      {{todo.autor}}
    </div>
    <div
      v-bind:class="{ 'from-left': todo.completed, 'from-right': !todo.completed }"
      class="nes-balloon is-dark"
    >
      <p>
        {{ todo.title }}
        <button class="nes-btn is-error" @click="$emit('delete-todo', todo.id)">X</button>
      </p>
    </div>
    <div v-if="!todo.completed">
      <i v-bind:class="todo.pokemon"></i>
      {{todo.autor}}
    </div>
  </div>
</template>
<script>
export default {
  name: "Todo",
  props: ["todo"]
};
</script>
<style scoped>
</style>