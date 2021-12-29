<template>
  <nav class="bg-green-400 text-white">
    <div class="container mx-auto">
      <div class="flex items-center text-2xl">
        <router-link to="/" class="inline-block px-10 py-6 transition-colors hover:bg-green-300 duration-300">Home</router-link>
        <router-link to="/todos" class="inline-block px-10 py-6 ml-8 transition-colors hover:bg-green-300 duration-300">Todos</router-link>
      </div>
    </div>
  </nav>

  <router-view />
</template>

<style>
#app {
  font-family: Poppins, Avenir, Helvetica, Arial, sans-serif;
}
</style>
