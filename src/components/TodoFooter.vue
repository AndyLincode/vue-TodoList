<template>
  <div class=" flex justify-around mt-3 w-1/2 mx-auto">
    <strong>尚有 <span class="text-red-600">{{ props.remaining }}</span> 個事項未完成</strong>
    <button class="bg-orange-500 w-32 rounded-xl text-white hover:bg-orange-700"
      @click="handleRemoveCompleted">清除已完成</button>
  </div>
</template>

<script setup>
const props = defineProps({ remaining: Number })
const emit = defineEmits(['removeCompleted'])
const handleRemoveCompleted = () => {
  emit('removeCompleted')
}
</script>

<style lang="scss" scoped>

</style>