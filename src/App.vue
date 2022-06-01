<template>
<div id="app">
  <h1>Conversor de Moedas</h1>
  <div class="linha">
    <Conversor :moedaA= "'BRL'" :moedaB="'USD'"/>
    <Conversor :moedaA= "'USD'" :moedaB="'BRL'"/>
  </div>
  <div class="linha">
    <Conversor :moedaA= "'BRL'" :moedaB="'EUR'"/>
    <Conversor :moedaA= "'EUR'" :moedaB="'BRL'"/>
  </div>
</div>
 
</template>

<script>

import Conversor from "./components/Conversor.vue"
export default {
  name: 'App',
  components: {
    Conversor
}
}
</script>

<style>
#app {
  margin: auto;
  max-width: 1000px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.linha{
  margin: 50px;
  display: flex;
  justify-content: space-around;
}
</style>
