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
    <h2> second header in Main.vue </h2>
    <ol>
      <li v-for="todo in to_dos" :key="todo.id">
        {{todo.text}}
      </li>
    </ol>
    
    <br>

    <ol>
      <li v-if="show">
        <span>if condition</span>
      </li>
      <li v-else>
        <span>else condition</span>
      </li>
    </ol>

    <h1> {{start}} </h1> <p>{{formattedElapsedTime}}</p>
    <button id="start-button" v-on:click="startFunction()">Start</button>
    <button id="stop-button" v-on:click="stopFunction()">Stop</button>
    <button id="start-quiz" @click.prevent="startQuiz(false)">Start Quiz</button>

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
      start:0,
      elapsedTime:0,
		};
	},
  computed: {
    formattedElapsedTime() {
      const date = new Date(null);
      date.setSeconds(this.elapsedTime / 1000);
      const utc = date.toUTCString();
      return utc.substr(utc.indexOf(":") - 2, 8);
    }
  },
  methods:{
    reset() {
      this.elapsedTime = 0;
    },
    /* start graphs etc */ 
    startFunction:function(){this.start=1;
      this.timer = setInterval(() => {
          this.elapsedTime += 1000;
        }, 1000);
    },
    /* stop graphs etc */
    stopFunction:function(){
      this.start=0;
      clearInterval(this.timer);
    },


    countDownTimer() {
			document.getElementById("timer").innerHTML =
				"Time remaining: " + this.timer;
			let interval = setInterval(() => {
				this.timer--;
				if (this.timer <= 0 || !this.playing) {
					this.timer = 0;
					document.getElementById("quiz").hidden = true;
					document.getElementById("score").hidden = false;
					document.getElementById("score").innerHTML =
					clearInterval(interval);
				}
				document.getElementById("count-down-timer").innerHTML =
					"Time remaining: " + this.timer;
			}, 1000);
		},


  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import '../assets/styles_main.css';
</style>
