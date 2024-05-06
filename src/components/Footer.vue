<template>
  <div class="footerbox">
    <span class="footertext">FILINGO &copy; {{ year }}</span>
    <br />
    <span class="text-xs">Enliven Technologies Philippines</span>
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
.footerbox {
  position: fixed;
  bottom: 0;
  background: #0faf87;
  height: 80px;
  width: 100%;
  padding: 20px;
  z-index: 1;
}
.footertext {
  font-family: Arvo;
}
</style>