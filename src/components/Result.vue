<template>
  <div class="card">
    <h4>Your result</h4>
    <p>{{ result }} seconds</p>
  </div>
</template>

<script>
export default {
  setup() {},
  props: ["result"],
  name: "GameResult",
};
</script>

<style scoped></style>
