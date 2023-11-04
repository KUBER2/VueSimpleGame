<template>
  <div class="card">
    <h1>Game block</h1>
    <button @click="clickHandler">Start the game!</button>
  </div>
</template>

<script>
export default {
  setup() {},
  name: "GameBlock",
  methods: {
    clickHandler() {},
    boxClick() {
      this.$emit("timer", 0.00932);
    },
  },
};
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
