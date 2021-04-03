<template>
  <div id="app">
    <div class="top">
      <div class="container-center">
        <div id="clockbox">
          <script src="clock.js"></script>
        </div>
        <h1>Header here</h1>
      </div>
      <p id="github_code">
        Code <a href="https://github.com/pisar-relva/telemetriaVue">here</a>
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
/* For the whole app */
* {
  box-sizing: border-box;
  margin: 0;
  font-family:Klavika Basic;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* header */
.top {
  background-color: #009de0;
  box-shadow:0px 5px 5px #D3D3D3;	
  font-size: 15px;
  display: flex;
}

/* "body" */
.container-center {
  display: flex;
  height: auto;
  width: auto;
  margin: auto;
}

/* h1 in header */
.top h1 {
    margin: 5px;
    color: white;
    font-size: 2.5em;
}

/* for the letters */
#github_code {
  float: right;
  color: white;
  /*font-weight: bold;*/
  font-size: 13px;
  margin: 5px;
}

 /* for the link */
#github_code a {
  color: white;
}

</style>
