<template>
  <div class="training">
    <h1>Math Trainer</h1>
    <Start v-if="current=='start'" @onStart="onStart" />
    <Question v-else-if="current=='question'" />
    <Message v-else-if="current=='message'" />
    <Result v-else-if="current=='result'" />
    <div v-else>unknown error</div>
  </div>
</template>

<script>
import Question from "./components/Question.vue";
import Message from "./components/Message.vue";
import Result from "./components/Result.vue";
import Start from "./components/Start.vue";

export default {
  name: "App",
  components: {
    Start,
    Question,
    Message,
    Result
  },
  data() {
    return {
      current: "start"
    };
  },
  methods: {
    onStart() {
      this.current = "question";
    }
  }
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 700px;
  margin: 20px auto;
}
.training {
}
h1 {
  background-color: rgb(78, 63, 167);
  margin: 30px 10px;
}
</style>
