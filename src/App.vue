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
      /* for clock */
      interval: null,
      time: null,
    };
  },
   beforeDestroy() {
    /* prevent memory leak */
    clearInterval(this.interval)
  },
  created() {
    // update the time every second
    this.interval = setInterval(() => {
      // Concise way to format time according to system locale.
      this.time = Intl.DateTimeFormat(navigator.language, {
        hour: 'numeric',
        minute: 'numeric',
        second: 'numeric',
        month: 'numeric',
        day: 'numeric',
        year: 'numeric'
      }).format()
    }, 1000)
  }

};
</script>

<style>
  @import './assets/styles_app.css';
</style>