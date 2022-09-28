<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <PokeLista />
</template>

<script>
import PokeLista from './components/PokeLista.vue'

export default {
  name: 'App',
  components: {
    PokeLista
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body{
  background-color: #eb4d4b;
}
</style>
