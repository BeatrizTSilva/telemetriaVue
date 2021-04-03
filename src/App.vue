<template>
  <div id="app">
    <div class="top">
      <div class="container-center">
        <div id="clockbox">
          <!--script src="clock.js"></script-->
        </div>
        <h1>Header here</h1>
      </div>
      <p id="github_code">
        Code <a href="https://github.com/pisar-relva/telemetriaVue" target="_blank" rel="noopener noreferrer">here</a>
      </p>
    </div>
    <Main />
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main,
  },
};
</script>

<style>
  @import './assets/styles_app.css';
</style>