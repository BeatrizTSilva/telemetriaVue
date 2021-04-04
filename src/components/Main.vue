<template>
  <div id="big-container">
    <!--div id="header">
      <div id="clockbox">
        <h2> second header </h2>
      </div>
    </div-->
    <!--div id="something">
      <p>in id=body</p>
    </div-->
    <!--ToggleButton /-->
    <p id="state">{{state}}</p>
    <p id="elapsedTime">{{formattedElapsedTime}}</p>
    
    
    <h2> second header in Main.vue </h2>
    <ol>
      <li v-for="todo in to_dos" :key="todo.id">
        {{todo.text}}
      </li>
    </ol>

    <ol>
      <li v-if="show">
        <span>if condition</span>
      </li>
      <li v-else>
        <span>else condition</span>
      </li>
    </ol>

    
    <button id="start-button" v-on:click="startFunction()">Start</button>
    <button id="stop-button" v-on:click="stopFunction()">Stop</button>
    <button id="reset-button" v-on:click="resetFunction()">Reset</button>

  </div>
</template>

<script>
//import Clock from 'components/Clock.vue' --> this path is wrong
export default {
  name: 'Main',
  /*components: {
    ToggleButton,
  },*/
  
  // "data()" guarda variáveis de estado
  data() {
		return {
			to_dos: [{text:'vue js'} , {text:'react js'}, {text:'angular'}],
      show:false,
      state:"Waiting...",
      elapsedTime:0,
		};
	},
  computed: {
    /* for counter clock */
    formattedElapsedTime() {
      const date = new Date(null);
      date.setSeconds(this.elapsedTime / 1000);
      const utc = date.toUTCString();
      return utc.substr(utc.indexOf(":") - 2, 8);
    }
  },
  methods:{
    /* start graphs etc */ 
    startFunction:function(){
      this.state="Started";
      this.timer = setInterval(() => {
          this.elapsedTime += 1000;
        }, 1000);
    },
    /* stop graphs etc */
    stopFunction:function(){
      this.state="Stopped";
      clearInterval(this.timer);
    },
    /* reset graphs etc */
    resetFunction() {
      this.state="Reset";
      this.elapsedTime = 0;
    },
  }
}
</script>

<style scoped>
  @import '../assets/styles_main.css';
</style>
