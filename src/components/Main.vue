<template>
  <div id="big-container">
    <div id="logo">
      
    </div>
    <!--div id="header">
      <div id="clockbox">
        <h2> second header </h2>
      </div>
    </div-->
    <!--div id="something">
      <p>in id=body</p>
    </div-->

    <h2> second header in Main.vue </h2>
    <!--ol>
      <li v-for="todo in todos" :key="todo.id">
        {{todo}}

      </li>
    </ol-->




  </div>
  
  
</template>

<script>
export default {
  name: 'Main',
  // "data()" guarda variáveis de estado
  data() {
		return {
			todos: ['vue js', 'react js', 'angular']
		};
	},
  props: {
    msg: String,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import '../assets/styles_main.css';
</style>
