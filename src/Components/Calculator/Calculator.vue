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
<template src="./Calculator.html"/>
<style src="./Calculator.css"/>
