<template>
  <section class="nes-container with-title">
    <h3 class="title">
      <i class="nes-icon trophy"></i>
      La frase más votada es...</h3>
    <div class="row">
      <div class="col-xs">
        <div class="box">
          <div class="avatar">
            <img class="nes-avatar is-large image is-rounded" v-bind:src="require('../assets/' + mostVoted.picture)" />
          </div>
          {{mostVoted.autor}}
        </div>
      </div>
      <div class="col-xs">
        <div class="box">
          <div class="nes-balloon from-left">
            <p>{{mostVoted.title}}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "MostVoted",
  props: ["mostVoted"]
};
</script>
<style scoped>
.image {
 width: 80%;
  height: auto;
  image-rendering: pixelated;
}
</style>