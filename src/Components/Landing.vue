<template>
  <div class="hello uk-width-1-1 uk-container uk-container-center" uk-grid>
    <div class="info uk-width-1-3 uk-margin-auto uk-padding-large uk-align-center">
      <h1>{{ msg }}</h1>
      <p>
        Amount of credit: £{{}} over 4 months. Interest: £170.45. Interest rate: 274%pa (fixed).
        Repay with 4 payments: 1st payment £142.50, 2nd payment £125.63, 3rd payment £109.88, 4th payment £92.44. Total amount payable: £470.45. Representative 1079.24% APR
      </p>
    </div>
  </div>
</template>

<script>

export default {
  name: "Landing",
  props: {
    msg: String
  },
  data(){
    return{
      server:null,
    }
  },
  created(){
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
.hello{
  background: #eeefef;
  box-shadow: inset 0px 5px 10px -5px rgba(0,0,0,0.75);
}
</style>
