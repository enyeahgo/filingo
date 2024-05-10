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
          <div class="flex justify-content-center" style="align-items: center;">
            <img :src="getImage(navItem.icon)" width="30px" height="30px" />&nbsp;{{ navItem.name }}
          </div>
        </button>
      </nav>
      <div v-for="tabItem in tabItems" :key="tabItem.name" class="flex justify-center align-center">
        <div v-show="isActive(tabItem.name)" class="p-4 w-full lg:w-1/2 border rounded-md">
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
        { name: 'Points', icon: 'mangopoint.png' },
        { name: 'Stars', icon: 'starcoin.png' },
        { name: 'Credits', icon: 'pesocredit.png' },
      ],
      tabItems: [
        { name: 'Points', content: 'Welcome to the Home tab!' },
        { name: 'Stars', content: 'Learn more about us on the About tab.' },
        { name: 'Credits', content: 'Get in touch with us on the Contact tab.' },
      ],
      active: 'Points',
    };
  },
  methods: {
    setActive(name) {
      this.active = name;
    },
    isActive(name) {
      return this.active === name;
    },
    getImage(img) {
      return require(`../assets/${img}`);
    }
  },
};
</script>

<style scoped>
/* Add any additional styles for customization here */
</style>
