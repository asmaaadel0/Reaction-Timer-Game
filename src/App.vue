<template>
  <h1>Reaction Timer</h1>
  <button @click="startGame" :disabled="isStarting">Start</button>
  <div v-if="isStarting">
    <the-block :delay="delay" @end="endGame"></the-block>
  </div>
  <the-results v-if="showResult" :score="score"></the-results>

</template>

<script>
import TheBlock from './components/TheBlock.vue';
import TheResults from './components/TheResults.vue';

export default {
  name: 'App',
  components: {
    TheBlock,
    TheResults
  },
  data() {
    return {
      isStarting: false,
      showResult: false,
      delay: null,
      score: null,
    }
  },
  methods: {
    startGame() {
      this.showResult = false;
      this.isStarting = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay);
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isStarting = false;
      this.showResult = true;
    }
  }

}
</script>

<style>
button {
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  font: inherit;
  background-color: #4fcfd4;
  border: 1px solid #4fcfd4;
  color: white;
  cursor: pointer;
  border-radius: 30px;
  margin-right: 0.5rem;
  display: inline-block;
}

button:hover,
button:active {
  background-color: #96e3e6;
  border-color: #96e3e6;
}

button[disabled] {
  opacity: 0.3;
  cursor: not-allowed;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
html{
  
  background-color: #f2fdfd;
}
</style>
