<template>
  <div>
    <form @submit="addTodo">
      <section class="nes-container with-title">
        <h3 class="title">Agregar Frase</h3>
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
            <option value="Saul">Saúl</option>
            <option value="Pedro">Pedro</option>
          </select>
        </div>
        <br />
        <button class="nes-btn is-primary" type="submit">Agregar</button>
      </section>
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
        position: this.position,
        picture: getPicture(this.autor)
      };
      this.$emit("add-todo", newTodoObj);
      this.title = "";
      this.autor = "";
      this.position = !this.position;
    }
  }
};

function getPicture(autor) {
  switch (autor) {
    case "Andrea": {
      return "andrea.jpg";
    }
    case "Via": {
      return "via.jpg";
    }
    case "Monse": {
      return "monse.jpg";
    }
    case "Laura": {
      return "laura.jpg";
    }
    case "Brenda": {
      return "brenda.jpg";
    }
    case "Saul": {
      return "saul.jpg";
    }
    case "Pedro": {
      return "pedro.jpg";
    }
  }
}
</script>
<style scoped>
</style>