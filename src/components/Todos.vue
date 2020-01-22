<template>
  <div>
    Vuex todo app
    <br />
    <div class="todos">
      <div class="todo" v-for="todo  in allTodos " :key="todo.id">
        {{todo.title}}
        <span class="delete" @click="deleteTodo(todo.id)">x</span>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Todos",
  methods: { ...mapActions(["fetchTodos", "deleteTodo"]) },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
};
</script>


<style scoped>
.todos {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
}

.todo {
  border: 1px solid white;
  background: red;
  color: white;
  padding: 1rem;
  border-radius: 5px;
  text-align: center;
  position: relative;
  cursor: pointer;
}

.delete {
  cursor: pointer;
  background: green;
  float: right;
  color: aliceblue;
}
</style>