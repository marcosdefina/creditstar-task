<template>
  <div class="calculator">
    <div class="title"></div>
    <div class="loan-slider">
    </div>
    <div class="time-slider"></div>
    <div class="day-picker"></div>
    <div class="day-picker"></div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator {
  display: flex;
  height: 420px;
  width: 80%;
  margin: 5vh auto;
  background-color: white;
  box-shadow: 0 1px 4px 2px rgba(0, 0, 0, 0.2);
  border-radius: 12px;
}

</style>
