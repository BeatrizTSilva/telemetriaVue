<template>
  <div id="app">
    <div id="header">
      <div id="clockbox">

      </div>
      
    </div>
    <!--img id="logo" src="./assets/rover.ico"-->
    <Main_file />
  </div>
</template>

<script>
import Main_file from '@/components/Main_file.vue'

export default {
  name: 'App',
  components: {
    Main_file
  }
}
</script>

<style>
/* Aplica-se a tudo */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
