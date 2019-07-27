<template>
  <div id="app">
    <Header/>
    <Design/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Design from './components/Design.vue'

export default {
  name: 'app',
  components: {
    Header,
    Design
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
}
img{
  height: 300px;
  width: 300px
}
</style>
