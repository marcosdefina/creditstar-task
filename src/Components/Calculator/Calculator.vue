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
      slider: {
        lineHeight: 10,
        processStyle: {
          backgroundColor: "#ffb700"
        }
      },

      pickedDay: new Date('02/07/2019'),
      yearlyInterest: 0.25,
      totalAmountToPay: this.TotalToPay(this.loan, this.time, this.pickedDay),
    };
  },
  methods: {
    InterestConverter: function(totalInterest, discreteInterval){
      return Math.pow((1+totalInterest),(1/discreteInterval));
    },
    TotalToPay: function(loan, months, pickedDay){
      //loan * monthsInterst*months + loan * (|now - pickedDay| * dailyInterest)
      var today = new Date();

      var monthlyInterest = this.InterestConverter(this.yearlyInterest, 12);
      
      if(this.formatDate(today) != this.formatDate(pickedDay))
        var dailyInterest = this.InterestConverter(this.yearlyInterest, 365.25);
      
      return loan * (Math.pow(monthlyInterest, months))// + (Math.pow(dailyInterest, this.dayModule(today, pickedDay))));
    },
    formatDate: function(date = new Date()){
      return (date.getMonth()+1)+'/'+date.getDate()+'/'+date.getFullYear();
    },
    dayModule: function(date1 = new Date(), date2  = new Date('01/01/2001')){
      const diffTime = Math.abs(date2.getTime() - date1.getTime());
      return Math.ceil(diffTime / (1000 * 60 * 60 * 24));
      //We could to discretize more and more until get fair.
      //But will never be fair until the discretization takes the limit to a continuous interval.
      //So lets round up.
    },
  },
  components: {
    VueSlider,
    Datepicker
  }
};

</script>
<template src="./Calculator.html"/>
<style src="./Calculator.css"/>
