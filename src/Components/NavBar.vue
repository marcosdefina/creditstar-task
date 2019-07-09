<template>
    <div class="nav">
      <i class="material-icons nav-icon-positioning">account_circle</i>
    </div>
</template>

<script>
export default {
  name: "navbar"
}
</script>

<style scoped>
.nav {
  background-color: #ffb700;
  width: 100%;
  height: 5vh;
  box-shadow: 0 1px 4px 2px rgba(0,0,0,0.2);
}
.nav-icon-positioning{
  display: flex;
  max-width: 24px;
  padding: 7px;  
}
</style>
