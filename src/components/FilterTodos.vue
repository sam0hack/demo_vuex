<template>
  <div>
    <h4>Filter Todo</h4>

    <select @change="filterTodos($event)">
      <option value="10">10</option>
      <option value="20">20</option>
      <option value="100">100</option>
      <option value="200">200</option>
    </select>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "FilterTodos",
  methods: mapActions(["filterTodos"])
};
</script>

<style scoped>
</style>