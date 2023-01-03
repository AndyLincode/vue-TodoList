<script setup>
import { ref } from 'vue';
const msg = ref('');
</script>

<template>
  <input type="text" v-model="msg" class="outline-black border border-black">
<p class="text-red-500 text-2xl">Hello {{msg}}</p>
</template>

<style scoped>

</style>