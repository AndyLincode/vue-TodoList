<template>
  <div class=" flex justify-center">
    <strong>尚有 <span class="text-red-600">{{ remaining }}</span> 個事項未完成</strong>
    <button class="bg-orange-500 w-44 rounded-xl text-white hover:bg-orange-700" @click="removeDone">清除已完成</button>
  </div>
  <p>{{ message }}</p>
</template>

<script setup>
const props = defineProps({
  message: String,
})
</script>

<style lang="scss" scoped>

</style>