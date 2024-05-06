<template>
  <div class="flex h-screen items-center justify-center">
    <p>FILINGO &copy; {{ year }}</p>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        year: '2023'
      }
    },
    mounted() {
      this.year = (new Date).toLocaleDateString('en-PH', {
        year: 'numeric'
      })
    }
  }
</script>

<style scoped>
#footercontainer {
  position: fixed;
  bottom: 0;
}
</style>