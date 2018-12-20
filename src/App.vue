<template>
  <div id="app">
    <img src="./assets/logo.png">
      <test-name></test-name>  
      <users></users>
  </div>
</template>

<script>
import TestName from './components/Test.vue'
import Users from './components/Users'
//import bridge from './vue-temp/vue-editor-bridge';

export default {
  name: 'app',
  components: {
    TestName, Users
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>




