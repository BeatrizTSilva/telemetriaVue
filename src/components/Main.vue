<template>
  <div id="body">
    <p>in id=body</p>
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
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import '../assets/styles_main.css';
</style>
