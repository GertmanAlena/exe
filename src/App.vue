<template>
  <div id="app">
    <HomeWork />
    <AuthenticationComponent />
    <CardComponent />
    <MortgageCalculator />
  </div>
</template>

<script>
import AuthenticationComponent from './components/AuthenticationComponent.vue'
import CardComponent from './components/CardComponent.vue'
import MortgageCalculator from './components/MortgageCalculator.vue'
import HomeWork from './components/HomeWork.vue'

export default {
  name: 'App',
  components: {
    AuthenticationComponent,
    CardComponent,
    MortgageCalculator,
    HomeWork
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
</style>
