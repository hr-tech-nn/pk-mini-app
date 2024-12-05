<script setup lang="ts">

</script>

<template>
<header class="fixed top-0 left-0 right-0 h-48px flex items-center justify-between bg-[#58595B] text-white z-10">
  <div class="flex items-center ">
    <img src="/pk-logo.svg" alt="Логотип" class="w-16 h-12 ml-4" />
  </div>
  <h1 class="text-xl font-bold mx-auto">Учебный центр</h1> <!-- Центрирование заголовка -->
  <div class="md:hidden">
    <button @click="toggleMenu" class="text-white bg-transparent rounded-full test">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-8 h-8">
        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16m-7 6h7" />
      </svg>
    </button>
  </div>
  <nav class="hidden md:flex space-x-4">
    <NuxtLink to="/" class="hover:underline">Главная</NuxtLink>
    <NuxtLink to="/about" class="hover:underline">О нас</NuxtLink>
    <NuxtLink to="/course" class="hover:underline">Контакты</NuxtLink>
  </nav>
</header>
</template>

<style scoped>
.test {
  border: none;
}
</style>