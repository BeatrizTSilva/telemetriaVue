<template>
  <div id="big-container">
    <div id="header">
      <div id="clockbox">
        <!--h2> {{msg}} </h2-->
        <h2> second header </h2>
      </div>
    </div>
    <div id="something">
      <p>in id=body</p>
    </div>
  </div>
  
  
</template>

<script>
export default {
  name: 'Main',
  // "data()" guarda variáveis de estado
  data() {
		return {
			customQuiz: [],
			questions: [],
			loading: true,
			playing: true,
			index: 0,
			score: 0,
			timer: 10,
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
