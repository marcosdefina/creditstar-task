<template>
  <div id="app">
    <div class="nav">
    </div>

    <Calculator></calculator>

    <img id="logo" alt="logo" src="./assets/logo.svg">
    <HelloWorld msg="Welcome to Credit Star"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Calculator from "./components/Calculator/Calculator.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    Calculator,
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
  background-size: 1366px 768px
}
.nav {
  background-color: #ffb700;
  width: 100%;
  height: 5vh;
  box-shadow: 0 1px 4px 2px rgba(0,0,0,0.2);
}


@media screen {
}
</style>
