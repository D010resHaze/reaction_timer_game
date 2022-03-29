<template>
  <p>Result - {{ resultScore }}ms</p>
  <div v-if="resultScore < 250">Shit man! You are so fast like a FLASH. How did you click that damn button?</div>
  <div v-else-if="resultScore >= 250 && resultScore < 500">Hmm, you did it bro. Your click level is normal. That's cool bro.</div>
  <div v-else>Damn bro, you are too slow! You can try again.<br>Long time ago, there is a quote from Sayar Chaink Kay Ko<br>"အရှုံးမပေးနဲ့ ကြိုးစား"</div>
</template>

<script>
export default {
  props: ['resultScore']
}
</script>

<style>

</style>