<template>
  <h1> Timer project</h1>
  <button @click="start" :disabled="isPlaying">PLay</button>
  <Block v-if="isPlaying" :dalay="delay" @end="endGame"/>
  <Results v-if="showScore" :score="score" />
</template>

<script>
import Block from './components/Block.vue'
import Results from "@/components/Results.vue";

export default {
  name: 'App',
  components: {
    Results,  Block
  },
  data(){
    return{
      delay: null,
      isPlaying: false,
      score: null,
      showScore: false,
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      console.log(this.delay)
      this.showScore = false
    },
    endGame(reationTime){
      this.score = reationTime
      this.isPlaying = false
      this.showScore= true

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #50d2f1;
  margin-top: 60px;
}
</style>
