<template>
  <div class="row">
    <div class="col-xs" v-if="todo.position">
      <i v-bind:class="todo.pokemon"></i>
      {{todo.autor}}
    </div>
    <div
      v-bind:class="{ 'from-left': todo.position, 'from-right': !todo.position }"
      class="nes-balloon is-dark col-xs-9"
    >
      <p>{{ todo.title }}</p>
      <p>
        0<i class="nes-icon is-small coin"></i>
      </p>
      <p></p>
    </div>
    <div class="col-xs" v-if="!todo.position">
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