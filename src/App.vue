<template>
  <div>
    <h1>Reaction Timer Game</h1>
    <button class="start_button" @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" @stop="endGame"></Block>
    <Results v-if="showResults" :reactionTime="reactionTime"></Results>
  </div>
</template>

<script>
import Block from './components/block.vue';
import Results from './components/results.vue';

export default {
  name: 'App',
  components: {
    Block, Results
  },

  data() {
    return {
      isPlaying: false,
      delay: null,
      reactionTime: null,
      showResults: false,
    }
  },

  methods: {
    start() {
      this.delay = 2000 + Math.random() * 4000;     
      this.showResults = false;
      this.isPlaying = true;      
      
    },
    endGame(reactionTime) {
      this.reactionTime = reactionTime;
      this.showResults = true;
      this.isPlaying = false;
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
  color: #2c3e50;
  margin-top: 60px;
}

.start_button{
  min-width: 100px;
  padding: 20px;

  background: aquamarine;
  border: 1px solid #496785;
  border-radius: 5px;
  box-shadow: 0px 5px 5px rgba(0,0,0,0.1);
}
</style>
