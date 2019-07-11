<template>
  <div id="app">

    <NavBar></NavBar>
    <div class="uk-container uk-container-center">
      <div uk-grid data-uk-grid-margin>
        <Calculator class="uk-width-1-3@l"></calculator>
      </div>
      <img id="logo" alt="logo" src="./assets/logo.svg">
    </div>
    <Landing msg="Welcome to Credit Star"/>

  </div>
</template>

<script>
import Landing from "./Components/Landing.vue";
import Calculator from "./Components/Calculator/Calculator.vue";
import NavBar from "./Components/NavBar.vue";

export default {
  name: "app",
  components: {
    Landing,
    Calculator,
    NavBar,
  }
};
</script>

<style>
body, html{
  margin: 0;
  padding: 0;
}
#logo{
  width: 200px;
  height: 200px;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #f5f5f5;
  background-image: url("./assets/images/city.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}

@media screen {
}
</style>
