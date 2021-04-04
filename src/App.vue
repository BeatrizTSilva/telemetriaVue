<template>
  <div id="app">
    <div class="top">
      <img id="psem-logo" src="../public/psem-car-white.png" />
      <div class="container-center">
        <!--div id="clockbox">
          <p>clockbox in app.vue</p>
        </div-->
        <h3>Header here in App.vue</h3>
      </div>
      <p id="github_code">
        Code <a href="https://github.com/pisar-relva/telemetriaVue" target="_blank" rel="noopenernoreferrer">here</a>
      </p>
    </div>
    <Main/>
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