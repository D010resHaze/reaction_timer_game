<template>
  <div class="block" @click="endTimer" v-if="showBlock">Click Here {{ delay }}</div>
</template>

<script>
export default {
  data() {
    return {
      showBlock: false,
      blockScore: 0,
      timer: null
    }
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.blockScore += 50;
        
      }, 50);
    },
    endTimer() {
      clearInterval(this.timer);
      this.$emit('endGame', this.blockScore);
    }
  },
  props: ['delay'],
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  }
}
</script>

<style>
  .block {
    width: 400px;
    margin: 50px auto;
    padding: 150px 0px;
    background: rgb(34,193,195);
    background: linear-gradient(0deg, rgba(34,193,195,1) 0%, rgb(222, 253, 45) 100%);
    color: #2c3e50;
  }
</style>