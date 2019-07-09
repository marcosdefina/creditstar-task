<template>
  <div class="calculator">
    <div class="title">
      <p>João Alfredo</p>
    </div>
    <div class="loan-slider">
      <div class="item-aligner">
        <p>Amount</p>
        <p>{{loan}} €</p>
        <i class="material-icons">add_circle</i>
        <i class="material-icons">remove_circle</i>
      </div>
      <vue-slider
        v-model="loan"
        :min="100"
        :max="700"
        :lineHeight="slider.lineHeight"
        :processStyle="slider.processStyle"
        :tooltip-formatter="loanFormatter"
      />
    </div>

    <div class="time-slider">
      <div class="item-aligner">
        <p>Period</p>
        <p>{{time}} Months</p>
        <i class="material-icons">add_circle</i>
        <i class="material-icons">remove_circle</i>
      </div>
      <vue-slider
        v-model="time"
        :min="1"
        :max="16"
        :lineHeight="slider.lineHeight"
        :processStyle="slider.processStyle"
      />
    </div>
    <div class="day-picker">
      <i class="material-icons">date_range</i>
      <datepicker style="
          display: inline-block;
          text-align: left;
        " />Pick a Date
    </div>
  </div>
</template>

<script>
import VueSlider from "vue-slider-component";
import "vue-slider-component/theme/default.css";
import Datepicker from "vuejs-datepicker";

export default {
  name: "Calculator",
  data() {
    return {
      value1: 0,
      formatter1: "{value}%",
      value2: 0,
      loanFormatter: v => `€${("" + v).replace(/\B(?=(\d{3})+(?!\d))/g, ",")}`,
      loan: 500,
      time: 7,
      styleTest: "transform: translate(" + translate_bar + "px,-15px)",
      slider: {
        lineHeight: 10,
        processStyle: {
          lineHeight: 10,
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
    VueSlider,
    Datepicker
  }
};

var translate_bar = -30;
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./styles/calculator.css">
.custom-tooltip.focus {
  font-weight: bold;
}
</style>
