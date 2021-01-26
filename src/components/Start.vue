<template>
  <div class="question">
    <h3>Are you ready?</h3>
    <button @click="$emit('onStart')">Start</button>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.question {
  background-color: rgb(78, 63, 167);
  text-align: center;
  margin: 30px 10px;
}
</style>