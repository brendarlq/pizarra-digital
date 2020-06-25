<template>
  <div class="row">
    <div class="col-xs" v-if="todo.position">
      <div class="avatar">
        <img v-bind:src="require('../assets/' + todo.picture)" class="image" />
      </div>
      {{todo.autor}}
    </div>
    <div
      v-bind:class="{ 'from-left': todo.position, 'from-right': !todo.position }"
      class="nes-balloon is-dark col-xs-9"
    >
      <p>{{ todo.title }}</p>
      <p class="col-xs-offset-11" v-on:click="addCont()">
        {{todo.cont}}
        <i v-repeat="10" class="nes-icon is-small heart"></i>
      </p>
      <p></p>
    </div>
    <div class="col-xs" v-if="!todo.position">
      <div class="avatar">
        <img v-bind:src="require('../assets/' + todo.picture)" class="image" />
      </div>
      {{todo.autor}}
    </div>
  </div>
</template>
<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    addCont() {
      this.todo.cont++;
    }
  }
};
</script>
<style scoped>
.image {
  width: 150px;
  border-radius: 2px;
  box-shadow: 1px 1px 3px 1px rgba(0, 0, 0, 0.5);
  transition: width 1s;
}
</style>