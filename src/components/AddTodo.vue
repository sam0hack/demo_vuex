<template>
  <div>
    <h3>Add todo</h3>

    <form @submit="onsubmit">
      <input type="text" v-model="title" placeholder="Add new Todo" />
      <input type="submit" value="submit" />
    </form>
  </div>
</template>


<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return { title: "" };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onsubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;

  outline: 0;
  border: 1px solid blue;
  cursor: pointer;
}

input[type="submit"] {
  flex: 2;
  background: cyan;
  color: black;
  border: 1px solid blue;
  cursor: pointer;
}
</style>