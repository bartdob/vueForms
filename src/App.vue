<template>
  <div id="app">
    <Forms/>
  </div>
</template>

<script>
import Forms from './components/Forms.vue'

export default {
  name: 'App',
  components: {
    Forms
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
