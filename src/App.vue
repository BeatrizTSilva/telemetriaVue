<template>
  <div id="app">
    <!--div id="top">
        <p>should be in the header</p>
    </div-->
    <div id="header">
      <div id="clockbox">
        <!--script src="clock.js"></script-->
        <p>clockbox</p>
      </div>
	  </div>
    <div class="container-center">
      <p id="github_code">
        code here <a href="https://github.com/pisar-relva/telemetriaVue">GitHub</a>
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
    Main
  }
}
</script>

<style>
/* For the whole app */
* {
  box-sizing: border-box;
  margin: 0;
  font-family:Klavika Basic;
}

/* contains container-center */
.top {
  background-color: #009de0;
  font-size: 14px;
  display: flex;
}

/* center */
.container-center {
  display: flex;
  height: auto;
  width: auto;
  margin: auto;
}

/* blue header and clock */
#header{
	padding:5.75px; text-align:center; background:#009de0; width:100%; font-size:15px;
	font-family:verdana; color:white; box-shadow:0px 5px 5px #D3D3D3;	
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/*#app {
  border:2px; font-family:Klavika Basic; margin:0px;
	background-color:white; color:#46555f;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/

/* for the letters */
#github_code {
  float: right;
  color: black;
  font-weight: bold;
}
 /* for the link */
#github_code a {
  color: black;
}

footer {
  position: fixed;
  bottom: 0;
  padding: 0.5rem 1rem;
  width: 100%;
  font-size: 0.7rem;
  background-color: #009de0;
}

</style>
