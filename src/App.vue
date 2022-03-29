<template>
  <h3>How fast can you catch me?<br>Catch me if you can!</h3>
  <button @click="startGame" :disabled="isPlaying">Play</button>

  <div v-if="isPlaying">
    <BlockComponent :delay="delay" @endGame="endGame" />
  </div>

  <div v-if="hideResult">
    <ResultComponent :resultScore="score" />
  </div>

</template>

<script>
import BlockComponent from './components/BlockComponent.vue'
import ResultComponent from './components/ResultComponent.vue'

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      hideResult: false,
      delay: null,
      score: 0
    }
  },
  methods: {
    startGame() {
      this.isPlaying = true;
      this.delay = 2000 + (Math.random() * 5000);
    },
    endGame(blockScore) {
      this.score = blockScore;
      this.isPlaying = false;
      this.hideResult = true
    }
  },
  components: {
    BlockComponent,
    ResultComponent
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
