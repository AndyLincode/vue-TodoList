<template>
  <div class=" rounded p-2 mt-2 text-center">
    <p class="text-2xl">TodoList</p>
  </div>
  <input type="text" name="item" id="item" v-model="newTodo" @keyup.enter="addTodo"
    class="block w-[300px] h-10 rounded-md border border-blue-500 pl-2 focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm mx-auto my-5"
    placeholder="輸入代辦事項">
  <TodoList :todos="todos.data"></TodoList>
  <TodoFooter :message="message"></TodoFooter>
</template>

<script setup>
import { ref, reactive } from 'vue';
import TodoFooter from '../components/TodoFooter.vue';
import TodoList from '../components/TodoList.vue';

const todos = reactive({
  "data": [
    { "id": 1, "title": "item1", "completed": false },
    { "id": 2, "title": "item2", "completed": true },
    { "id": 3, "title": "item3", "completed": false },
  ]
})


</script>

<style lang="scss" scoped>

</style>