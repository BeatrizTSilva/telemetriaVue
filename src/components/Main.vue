<template>
  <div id="big-container">
    <!--ToggleButton /-->
    <div id=stopwatch>
      <p id="elapsedTime">{{formattedElapsedTime}}</p>
      <p id="state">{{state}}</p>
    </div>
    <div class="buttons">
      <button id="start-button" v-on:click="startFunction()">Start</button>
      <button id="stop-button" v-on:click="stopFunction()">Stop</button>
      <button id="reset-button" v-on:click="resetFunction()">Reset</button>
    </div>
    <h2> second header in Main.vue </h2>
    <!--ol>
      <li v-for="todo in to_dos" :key="todo.id">
        {{todo.text}}
      </li>
    </ol-->

    <!--ol>
      <li v-if="show">
        <span>if condition</span>
      </li>
      <li v-else>
        <span>else condition</span>
      </li>
    </ol-->

    
    

  </div>
</template>

<script>

//import Clock from 'components/Clock.vue' --> this path is wrong
import './components/async_fulltable.js'
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
    /* for counter clock -> id="elapsedTime" */
    formattedElapsedTime() {
      const date = new Date(null);
      date.setSeconds(this.elapsedTime / 1000);
      const utc = date.toUTCString();
      return utc.substr(utc.indexOf(":") - 2, 8);
    }
  },
  methods:{
    /* start graphs etc -> id="elapsedTime" */ 
    startFunction:function(){
      this.state="Started";
      this.timer = setInterval(() => {
          this.elapsedTime += 1000;
        }, 1000);
    },
    /* stop graphs etc -> id="elapsedTime" */
    stopFunction:function(){
      this.state="Stopped";
      clearInterval(this.timer);
    },
    /* reset graphs etc -> id="elapsedTime" */
    resetFunction() {
      this.state="Reset";
      this.elapsedTime = 0;
    },
    database_connect (){
      const {DB} = require('./weird.js'); /* file for database parameters */
      const {Client} = require('pg'); /* will require the library Client */

      const client = new Client({ /* we need to send a json object */
        user: DB.username,
        host: DB.hostname,
        password: DB.database_password,
        port: 5432,
        database: DB.database_name
      })

      execute()

      async function execute (){ /* it will pause before going to the next method */
          try{
              await client.connect() /* returns a promise */
              console.log("Connected Successfully")
              const results = await client.query("SELECT * FROM " + DB.schema) /* you need to use await so that it doesnt execute automatically */
              console.table(results.rows)
          }
          catch (ex){
              console.log(`Something wrong happened ${ex}`)
          }
          finally{
              await client.end()
              console.log("Client disconnected successfully")
          }
      }

    },
  }
}
</script>

<style scoped>
  @import '../assets/styles_main.css';
</style>