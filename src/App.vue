<template>
  <div id="app">
    <ArithmeticCalculator />
  </div>
</template>

<script>
import ArithmeticCalculator from './components/ArithmeticCalculator.vue';

export default {
  name: 'App',
  components: {
    ArithmeticCalculator
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

#app {
  font-family: 'Roboto', sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
