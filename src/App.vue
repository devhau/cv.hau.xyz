<template>
  <CVTemplate/>
</template>

<script>
import CVTemplate from './components/CVTemplate.vue'

export default {
  name: 'App',
  components: {
    CVTemplate
  }
}
</script>

<style>
body,html{
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50; 
  background: #999;
  position: absolute;
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
  overflow: auto;
}
</style>
