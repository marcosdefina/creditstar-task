<template>
  <div class="calculator">
    <div class="title">
      <p>João Alfredo</p>
    </div>
    <div class="loan-slider">
      <div class="item-aligner">
        <p>Amount</p>
        <p>$23</p>
        <i>GI</i>
        <i>GI</i>
      </div>
      <div class="slider" v-on:click="incrementSlide">
        <div class="slide-bar"></div>
        <div class="slide-pin" v-bind:style="styleTest"></div>
      </div>
    </div>
    <div class="time-slider">
      <div class="item-aligner">
        <p>Period</p>
        <p>2Mth</p>
        <i>GI</i>
        <i>GI</i>
      </div>
      <div class="slider">
        <div class="slide-bar"></div>
        <div class="slide-pin2"></div>
      </div>
    </div>
    <div class="day-picker"></div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      styleTest: "transform: translate(" + translate_bar + "px,-15px)"
    };
  },
  methods: {
    incrementSlide() {
      this.translate_bar += 30;
      if (this.translate_bar > 160) this.translate_bar = -160;
    }
  }
};

var translate_bar = -30;
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./styles/calculator.css">
</style>
