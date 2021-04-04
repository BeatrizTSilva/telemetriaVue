<template>
  <div id="app">
    <div class="top">
      <img id="psem-logo" src="../public/psem-car-white.png" />
      <div class="container-center">
        <p id="clock">{{time}}</p> 
      </div>
      <p id="github_code">
        Code <a href="https://github.com/pisar-relva/telemetriaVue" target="_blank" rel="noopenernoreferrer">here</a>
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
  data() {
    return {
      /* for clock -> id="clock" */
      interval: null,
      time: null,
    };
  },
  /* prevent memory leak */
   beforeDestroy() {clearInterval(this.interval)},
   /* update the time every second -> id="clock" */
  created() {
    this.interval = setInterval(() => {
      this.time = Intl.DateTimeFormat(navigator.language, {
        hour: 'numeric', minute: 'numeric', second: 'numeric', month: 'numeric', day: 'numeric', year: 'numeric'
      }).format() }, 1000)
  }

};
</script>

<style>
  @import './assets/styles_app.css';
</style>