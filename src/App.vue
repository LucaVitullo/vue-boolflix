<template>
  <div id="app">
    <HeaderBoolfix />
  </div>
</template>

<script>
import HeaderBoolfix from './components/HeaderBoolfix.vue'

export default {
  name: 'App',
  components: {
    HeaderBoolfix,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
