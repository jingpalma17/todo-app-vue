<template>
  <div>
    <input type="text" v-model="name">
    <button @click="Create">Create</button>
  </div>
    <TodoList :TodoList="Todos" :Delete="Delete"/>
</template>

<script>
import TodoList from './TodoList.vue';
import { ref } from "@vue/runtime-core"

export default {
  name: 'Container',
  components: {
    TodoList
  },
  data() {
    return {
      name: "",
    };
  },
  setup() {
    let todoList = [
      { id: 1, name: 'Todo1' },
      { id: 2, name: 'Todo2' },
      { id: 3, name: 'Todo3' },
    ];
    return {
      Todos: ref(todoList)
    };
  },
  methods: {
    Create() {
      this.Todos.push({ id: this.Todos.length + 1, name: this.name });
      this.name = "";
      console.log(this);
    },
    Delete(idx) {
      this.Todos.splice(idx, 1);
    }
  }
}
</script>

<style>

</style>
