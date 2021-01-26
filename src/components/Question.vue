<template>
  <div class="question">
    <h3>{{ x }} + {{ y }} = {{answer}}</h3>
    <div class="buttons">
      <button v-for="button in answers" v-bind:key="button[key]">{{button}}</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      x: randNumbers(100, 200),
      y: randNumbers(100, 200)
    };
  },
  computed: {
    answers() {
      let good = this.x + this.y;
      let buttons = [good];
      while (buttons.length < 4) {
        let num = randNumbers(good - 10, good + 10);
        if (buttons.indexOf(num) === -1) {
          buttons.push(num);
        }
      }
      return buttons;
    }
  }
};
const randNumbers = (min, max) => {
  let diff = max - min;
  return Math.floor(Math.random() * (diff + 1)) + min;
};
</script>
<style scoped>
.question {
  background-color: rgb(196, 190, 228);
  text-align: left;
  margin: 30px 10px;
}
</style>