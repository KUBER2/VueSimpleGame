<template>
  <GameBlock @timer="timerHandler" />
  <GameResult v-if="isGameEnded" :result="result" />
</template>

<script>
import GameBlock from "./components/Block.vue";
import GameResult from "./components/Result.vue";

export default {
  name: "App",
  components: {
    GameBlock,
    GameResult,
  },
  data() {
    return {
      result: "0.09931",
      isGameEnded: false,
    };
  },
  methods: {
    timerHandler(t) {
      console.log(t);
      this.result = t;
      this.isGameEnded = true;
    },
  },
};
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
body {
  margin: auto;
}
h1 {
  font-weight: 700;
  font-size: x-large;
}
.card {
  margin: auto;
  width: 450px;
  box-shadow: 5px 5px 5px 5px #808080;
  border-radius: 15px;
  margin-top: 20px;
  margin-bottom: 10px;
  min-height: 100px;
  padding: 15px;
  background-color: pink;
}
:root {
  --background: #e5ffb3;
  --background-accent: #dbf8a3;
  --background-accent-2: #bde66e;
  --light: #92de34;
  --dark: #69bc22;
  --text: #025600;
}
</style>
