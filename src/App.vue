<template>
  <h1>Reaction Timer</h1>
  <button @click="startGame">Start</button>
  <div v-if="isStarting">
    <the-block :delay="delay"></the-block>
  </div>
</template>

<script>
import TheBlock from './components/TheBlock.vue';
export default {
  name: 'App',
  components: {
    TheBlock,
  },
  data() {
    return {
      isStarting: false,
      delay: null,
    }
  },
  methods: {
    startGame() {
      this.isStarting = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay);
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
</style>
