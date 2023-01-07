<script setup>
import HelloWorld from '@/components/HelloWorld.vue'
import NavbarVue from './components/Navbar.vue';
import '@/assets/index.css'
import { ref, computed } from 'vue';

const data = ref(0);

const newData = computed({
  get: () => data.value,
  set: (val) => {
    data.value = val; // 不寫就不改變
  }
})

console.log(newData.value);

newData.value = 3;

console.log(newData.value);



</script>



<template>
  <NavbarVue></NavbarVue>
  <router-view></router-view>
</template>


<style scoped>

</style>
