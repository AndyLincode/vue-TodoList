<template>
  <ul class="list container flex flex-col items-center">
    <li v-for="(todo, i) in props.todos" :key="todo.id"
      class="flex justify-between items-center text-2xl my-2  w-[300px] bg-slate-200 rounded p-2 text-cyan-500">
      <div v-if="editedTodo !== todo" class="flex items-center">
        <input type="checkbox" v-model="todo.completed" name="completed" id="completed" class="cursor-pointer">
        <p class="ml-2" :class="{ 'line-through text-gray-500': todo.completed }" @dblclick="editTodo(todo)">
          {{ todo.title }}</p>
      </div>
      <input type="text" class="block w-1/2 h-8 rounded-md border border-blue-500 pl-2  sm:text-sm  "
        placeholder="修改代辦事項" v-else v-model="todo.title" @keyup.enter="doneEdit(todo)" @blur="doneEdit(todo)"
        @keyup.esc="cancelEdit(todo)">
      <div @click="handleRemove(i)"
        class="text-white bg-red-600 rounded-full w-6 h-6 cursor-pointer text-lg flex items-center justify-center">
        <p>X</p>
      </div>
    </li>
  </ul>
</template>

<script setup>
// 接收父傳子
const props = defineProps({
  todos: Array,
})
// 子傳父
const emit = defineEmits(['removeTodo'])
const handleRemove = index => {
  // 第一個參數 引發父組件的 removeTodo 事件
  // 第二個參數 傳遞到 removeTodo 事件發生要執行的方法的資料
  emit('removeTodo', index)
}
</script>

<style lang="scss" scoped>
// scoped 只用此 component 的 style
</style>