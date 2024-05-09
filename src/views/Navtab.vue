<template>
  <div class="container mx-auto">
    <div class="mb-4">
      <nav class="d-flex justify-content-center mb-2">
        <button 
          v-for="navItem in navItems" 
          :key="navItem.name" 
          class="px-3 py-2 rounded-md text-gray-700 hover:text-blue-500 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 active:text-blue-500 active:font-bold"
          :class="{ 'bg-blue-100': isActive(navItem.name) }"
          @click="setActive(navItem.name)"
        >
          <div class="d-flex">
            <img src="../assets/starcoin.png" width="30px" height="30px" />
            <span>{{ navItem.name }}</span>
          </div>
        </button>
      </nav>
      <div v-for="tabItem in tabItems" :key="tabItem.name">
        <div v-show="isActive(tabItem.name)" class="p-4 border rounded-md">
          {{ tabItem.content }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navItems: [
        { name: 'Home', icon: '../assets/starcoin.png' },
        { name: 'About', icon: '../assets/starcoin.png' },
        { name: 'Contact', icon: '../assets/starcoin.png' },
      ],
      tabItems: [
        { name: 'Home', content: 'Welcome to the Home tab!' },
        { name: 'About', content: 'Learn more about us on the About tab.' },
        { name: 'Contact', content: 'Get in touch with us on the Contact tab.' },
      ],
      active: 'About',
    };
  },
  methods: {
    setActive(name) {
      this.active = name;
    },
    isActive(name) {
      return this.active === name;
    },
  },
};
</script>

<style scoped>
/* Add any additional styles for customization here */
</style>
