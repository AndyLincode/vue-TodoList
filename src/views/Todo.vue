<template>
  <div class=" rounded p-2 mt-2 text-center">
    <p class="text-2xl">TodoList</p>
  </div>
  <input type="text" name="item" id="item" v-model.trim="newTodo" @keyup.enter="addTodo"
    class="block w-[300px] h-10 rounded-md border border-blue-500 pl-2 focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm mx-auto my-5"
    placeholder="輸入代辦事項">
  <TodoList :todos="todos.data" @removeTodo="removeTodo"></TodoList>
  <TodoFooter :remaining="remaining" @removeCompleted="removeCompleted"></TodoFooter>
</template>

<script setup>
import { ref, reactive, watch, computed } from 'vue';
import TodoFooter from '../components/TodoFooter.vue';
import TodoList from '../components/TodoList.vue';

const todos = reactive({
  // 從 localStorage 中讀取資料
  "data": JSON.parse(localStorage.getItem('todos') || '[]')
})

const newTodo = ref('')
// 新增
const addTodo = () => {
  if (!newTodo.value) {
    return
  }
  todos.data.push({ "id": todos.data.length > 0 ? todos.data[todos.data.length - 1].id + 1 : 1, "title": newTodo.value, "completed": false })
  newTodo.value = '';
}
// 從子組間傳遞要刪除的 todo 到父組件
const removeTodo = index => {
  todos.data.splice(index, 1)
}

// 將資料儲存在 localStorage 中
watch(todos, (newTodos, oldTodos) => {
  localStorage.setItem('todos', JSON.stringify(newTodos.data))
}, { deep: true })

const remaining = computed(() => {
  let activeTodos = todos.data.filter(todo => !todo.completed)
  return activeTodos.length
})

const removeCompleted = () => {
  const doneItem = todos.data.filter(e => !e.completed);
  todos.data = doneItem;
}

</script>

<style lang="scss" scoped>

</style>