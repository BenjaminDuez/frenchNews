<template>
  <div id="app">
    <img src="./assets/france.gif" alt="drapeau de france">
    <h1>French News</h1>
    <h2>Bienvenue sur le site FrenchNews, le plus grands site d'information français.</h2>
    <section>
      <HelloWorld></HelloWorld>
    </section>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
