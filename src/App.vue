<template>
  <div id="app">
    <THWebHeader></THWebHeader>
  </div>
</template>

<script>
  import THWebHeader from './components/Header.vue'

  export default {
    name: 'app',
    components: {
      THWebHeader
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>