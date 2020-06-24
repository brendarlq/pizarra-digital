<template>
  <div>
    <form @submit="addTodo">
      <div class="nes-field">
        <label for="name_field">Frase</label>
        <input type="text" v-model="title" id="title" class="nes-input" />
      </div>
      <label for="default_select">Autor</label>
      <div class="nes-select">
        <select required id="autor" v-model="autor">
          <option value disabled selected hidden>Select...</option>
          <option value="Andrea">Andrea</option>
          <option value="Laura">Laura</option>
          <option value="Monse">Monse</option>
           <option value="Via">Via</option>
           <option value="Brenda">Brenda</option>
        </select>
      </div>
      <button class="nes-btn" type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuid } from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
      position: true
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
        id: uuid.v4,
        title: this.title,
        autor: this.autor,
        completed: this.position,
        pokemon: "nes-pokeball"
      };
      this.$emit("add-todo", newTodoObj);
      this.title = "";
      this.autor = "";
      this.position =!this.position;
    }
  }
};
</script>
<style scoped>
</style>