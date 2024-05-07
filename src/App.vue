<template>
  <header class="flex justify-between items-center px-4 py-4 bg-gray-800 text-white lg:px-20">
    <h1 class="title text-2xl font-bold">Filingo</h1>
  
    <nav class="hidden lg:flex space-x-4">
      <router-link to="/" class="hover:text-gray-400">Home</router-link>
      <router-link to="/about" class="hover:text-gray-400">About</router-link>
      <router-link to="/services" class="hover:text-gray-400">Services</router-link>
      <router-link to="/contact" class="hover:text-gray-400">Contact</router-link>
    </nav>
  
    <button id="menu-btn" class="lg:hidden focus:outline-none" @click="showMenu">
      <svg class="h-6 w-6 fill-current text-white" viewBox="0 0 24 24" ref="burger">
        <path fill-rule="evenodd" d="M4 6h16v2H4zm0 5h16v2H4zm0 5h16v2H4z" clip-rule="evenodd" />
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="15" height="15" stroke="white" fill="white" class="hidden mr-1" ref="cross"><g id="_01_align_center" data-name="01 align left"><polygon points="24 1.414 22.586 0 12 10.586 1.414 0 0 1.414 10.586 12 0 22.586 1.414 24 12 13.414 22.586 24 24 22.586 13.414 12 24 1.414"/></g></svg>
    </button>
  </header>
  
  <div class="hidden fixed top-0 left-0 h-screen w-64 bg-gray-800 text-white shadow-lg overflow-y-auto" ref="menu">
    <h2 class="title text-xl font-bold px-4 py-2">Filingo</h2>
    <ul class="px-4 py-2">
      <li><router-link to="/" class="hover:text-gray-400 block px-4 py-2" @click="showMenu">Home</router-link></li>
      <li><router-link to="/about" class="hover:text-gray-400 block px-4 py-2" @click="showMenu">About</router-link></li>
      <li><router-link to="/services" class="hover:text-gray-400 block px-4 py-2" @click="showMenu">Services</router-link></li>
      <li><router-link to="/contact" class="hover:text-gray-400 block px-4 py-2" @click="showMenu">Contact</router-link></li>
    </ul>
  </div>
  <div class="flex-grow px-4 py-4"></div>
  
  <router-view/>
  
  <Footer />
  
</template>

<script>
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: { Footer },
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
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.title {
  font-family: 'Briem Hand', Helvetica, Arial, sans-serif;
  font-size: 30px;
}
.sidebar {
  background: rgba(0, 0, 0, 0.5);
}
</style>
