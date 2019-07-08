<template>
  <div class="calculator">
    <div class="title">
      <p>João Alfredo</p>
    </div>
    <div class="loan-slider">
      <div class="item-aligner">
        <p>Amount</p>
        <p>{{loan}} €</p>
        <i>GI</i>
        <i>GI</i>
      </div>
      <VueSlideBar
        v-model="loan"
        :data="slider.loanSteps"
        :min="100"
        :max="700"
        :processStyle="slider.processStyle"
        :lineHeight="slider.lineHeight"
        :tooltipStyles="{ backgroundColor: 'red', borderColor: 'red' }"
        @callbackRange="callbackRange"
      />
    </div>

    <div class="time-slider">
      <div class="item-aligner">
        <p>Period</p>
        <p>{{time}} Months</p>
        <i>GI</i>
        <i>GI</i>
      </div>
      <VueSlideBar
        v-model="time"
        :min="1"
        :max="16"
        :processStyle="slider.processStyle"
        :lineHeight="slider.lineHeight"
        :tooltipStyles="{ backgroundColor: 'red', borderColor: 'red' }"
      />
    </div>
    <div class="day-picker"></div>
  </div>
</template>

<script>
import VueSlideBar from "vue-slide-bar";

export default {
  name: "Calculator",
  data() {
    return {
      loan: 500,
      time: 7,
      styleTest: "transform: translate(" + translate_bar + "px,-15px)",
      slider: {
        loanSteps: [100, 200, 300, 400, 500, 600, 700],
        lineHeight: 10,
        processStyle: {
          backgroundColor: "#ffb700"
        }
      }
    };
  },
  methods: {
    incrementSlide() {
      this.translate_bar += 30;
      if (this.translate_bar > 160) this.translate_bar = -160;
    }
  },
  components: {
    VueSlideBar
  }
};

var translate_bar = -30;
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./styles/calculator.css">
</style>
