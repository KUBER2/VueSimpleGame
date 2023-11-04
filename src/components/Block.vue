<template>
  <div class="card">
    <h1>Game block</h1>
    <button @click="clickHandler" :disabled="isButtonDisabled">
      {{ buttonDescription }}
    </button>
  </div>
  <SquareBox v-if="showBox" @boxClick="boxClick"></SquareBox>
</template>

<script>
import SquareBox from "./Square.vue";
export default {
  setup() {},
  name: "GameBlock",
  components: {
    SquareBox,
  },
  methods: {
    clickHandler() {
      console.log("Button has been clicked");
      this.isButtonDisabled = true;
      this.buttonDescription = "Wait for square";
      setTimeout(() => {
        this.showBox = true;
        this.timer = Date.now();
      }, getRandomInt(1 * 100, 3 * 1000));
    },
    boxClick() {
      this.isButtonDisabled = false;
      this.showBox = false;
      this.$emit("timer", (Date.now() - this.timer) / 1000);
    },
  },
  data() {
    return {
      showBox: false,
      isButtonDisabled: false,
      timer: 0,
      buttonDescription: "Click to start!",
    };
  },
};
function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min) + min); // The maximum is exclusive and the minimum is inclusive
}
</script>

<style scoped>
button {
  margin: auto;
  display: block;
  cursor: pointer;
  outline: none;
  border: none;
  background-color: var(--light);
  width: 250px;
  height: 50px;
  border-radius: 15px;
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--text);
  background-size: 100% 100%;
  box-shadow: 0 0 0 7px var(--light) inset;
  margin-bottom: 15px;
}
</style>
