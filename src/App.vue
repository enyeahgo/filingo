<template>
  <header class="flex justify-between items-center px-4 py-4 bg-gray-800 text-white lg:px-20">
    <h1 class="text-xl font-bold">Filingo</h1>
  
    <nav class="hidden lg:flex space-x-4">
      <a href="#" class="hover:text-gray-400">Home</a>
      <a href="#" class="hover:text-gray-400">About</a>
      <a href="#" class="hover:text-gray-400">Services</a>
      <a href="#" class="hover:text-gray-400">Contact</a>
    </nav>
  
    <button id="menu-btn" class="lg:hidden focus:outline-none" @click="showMenu">
      <svg class="h-6 w-6 fill-current text-white" viewBox="0 0 24 24" ref="burger">
        <path fill-rule="evenodd" d="M4 6h16v2H4zm0 5h16v2H4zm0 5h16v2H4z" clip-rule="evenodd" />
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="20" height="20" fill="white" class="hidden" ref="cross"><g id="_01_align_center" data-name="01 align center"><polygon points="24 1.414 22.586 0 12 10.586 1.414 0 0 1.414 10.586 12 0 22.586 1.414 24 12 13.414 22.586 24 24 22.586 13.414 12 24 1.414"/></g></svg>
    </button>
  </header>
  <div class="hidden flex space-x-4" ref="menu">
    <div class="fixed top-0 left-0 h-screen w-64 bg-gray-800 text-white shadow-lg overflow-y-auto">
      <h2 class="text-xl font-bold px-4 py-2">Filingo</h2>
      <ul class="px-4 py-2">
        <li><a href="#" class="hover:text-gray-400 block px-4 py-2">Home</a></li>
        <li><a href="#" class="hover:text-gray-400 block px-4 py-2">About</a></li>
        <li><a href="#" class="hover:text-gray-400 block px-4 py-2">Services</a></li>
        <li><a href="#" class="hover:text-gray-400 block px-4 py-2">Contact</a></li>
      </ul>
    </div>
    <div class="flex-grow px-4 py-4">
      </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: { },
  methods: {
    showMenu() {
      this.$refs.menu.classList.toggle('hidden');
      this.$refs.cross.classList.toggle('hidden');
      this.$refs.burger.classList.toggle('hidden');
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
