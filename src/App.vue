<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <CalcVida></CalcVida>
</template>

<script>
import CalcVida from './components/CalcVida.vue'

export default {
  name: 'App',
  components: {
    CalcVida
  }
}
</script>

<style>
body {
  background-color: #2c3e50;
  margin-left: 0%;
  margin-right: 0%;
}
#app {
  background-color: cadetblue;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 8%;
  margin-bottom: 5%;
  height: 100%;
  width: 100%;
}
#fam, #her, #gov, #sal, #empre, #par, #hij, #deud {
  margin-top: 0.5%;
  margin-bottom: 0.5%;
}
</style>
