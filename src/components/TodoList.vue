<template>
    <ul>
        <li v-for="(todoList, idx) in TodoList" :key="idx">
            <span>{{todoList.name}}</span><button @click="Delete(idx)">x</button>
        </li>
    </ul>
</template>

<script>
export default {
  name: 'TodoList',
  props: {
      TodoList: Array,
      Delete: Function
  }
}
</script>

<style>
</style>
