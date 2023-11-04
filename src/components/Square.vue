<template>
  <div class="backDrop">
    <div class="square" @click="clickHandler">
      <h1>Click me!</h1>
    </div>
  </div>
</template>

<script>
export default {
  setup() {},
  name: "SquareBox",
  methods: {
    clickHandler() {
      this.$emit("boxClick");
    },
  },
};
</script>

<style scoped>
.square {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 400px;
  height: 400px;
  margin-left: -200px;
  margin-top: -200px;
  background-color: rgba(23, 58, 175, 1);
  border-radius: 10px;
  z-index: 4;
}
.backDrop {
  top: 0;
  position: fixed;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  min-height: 200px;
  z-index: 2;
}
</style>
