<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Amount of credit: £300 over 4 months. Interest: £170.45. Interest rate: 274%pa (fixed).
      Repay with 4 payments: 1st payment £142.50, 2nd payment £125.63, 3rd payment £109.88, 4th payment £92.44. Total amount payable: £470.45. Representative 1079.24% APR
    </p>
  </div>
</template>

<script>
export default {
  name: "Landing",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
