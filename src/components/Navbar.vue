<template>
  <div class="shadow-md w-full fix left-0 top-0">
    <div class="md:flex items-center justify-between bg-white py-4 md:px-10 px-3">
      <div class="font-bold text-2xl cursor-pointer flex items-center font-mono text-yellow-800">
        <span class="text-3xl text-yellow-800 mx-2"><i class="fa-regular fa-paw"></i></span>
        PET
      </div>


      <div class="text-2xl absolute right-6 top-5 text-yellow-800 cursor-pointer md:hidden z-[2]">

      </div>
      <ul
        class="md:flex items-center absolute md:static bg-white md:z-auto z-[1] left-0 w-full md:w-auto md:pl-0 pl-6 transition-all duration-500 ease-in  md:opacity-100 ">
        <li key={link.name} className="md:ml-5 text-xl text-yellow-800 md:my-0 my-6 cursor-pointer">
          <router-link to='/'>Home</router-link>
        </li>
        <li key={link.name} className="md:ml-5 text-xl text-yellow-800 md:my-0 my-6 cursor-pointer">
          <router-link to='/about'>About</router-link>
        </li>
        <li key={link.name} className="md:ml-5 text-xl text-yellow-800 md:my-0 my-6 cursor-pointer">
          <router-link to='/todo'>Todo</router-link>
        </li>

      </ul>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>

