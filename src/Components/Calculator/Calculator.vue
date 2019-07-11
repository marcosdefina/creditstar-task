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
        processStyle: {
          backgroundColor: "#ffb700"
        }
      },
      pickedDay: new Date(),
      yearlyInterest: 0.25,
      totalAmountToPay: this.TotalToPay(this.loan, this.time, this.pickedDay),
      instalments: this.generalteListOfInstalments(),
      date:{
        disabledDates:{
          to: new Date(),
        }
      }
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
      
      var dailyInterest = this.InterestConverter(this.yearlyInterest, 365.25);
      
      //Aiming in the readability
      var totalMonthlyInterest = Math.pow(monthlyInterest, months);
      var numberOfDays = this.dayModule(today, pickedDay); //days between the starting of the loan until the first instalment
      var totalDailyInterest = Math.pow(dailyInterest, numberOfDays)-1;
      
      var result = loan * (totalMonthlyInterest + totalDailyInterest);

      return result;
    },
    formatDate: function(date = new Date()){
      return (date.getMonth()+1)+'/'+date.getDate()+'/'+date.getFullYear();
    },
    dayModule: function(date1 = new Date(), date2  = new Date()){
      const diffTime = Math.abs(date2.getTime() - date1.getTime());
      return Math.ceil(diffTime / (1000 * 60 * 60 * 24));
      //We could to discretize more and more until get fair.
      //But will never be fair until the discretization takes the limit to a continuous interval.
      //So lets round up.
    },
    generalteListOfInstalments(){
      var list = [];
      var totalToPay = this.TotalToPay(this.loan, this.time, this.pickedDay);
      for(instalment in Array(this.time).keys()){
        list.push(totalToPay/this.time);
      }
      console.log(list)
      return list;
    }
  },
  components: {
    VueSlider,
    Datepicker
  }
};

</script>
<template src="./Calculator.html"/>
<style src="./Calculator.css"/>
