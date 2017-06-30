<template>
  <div id="app">
    
    <users></users>
    <!--<myComponent something="hi there"></myComponent>-->
  </div>
</template>

<script>
import myComponent from './components/myComponent'
import Users from './components/Users'

export default {
  name: 'app',
  components: {
    myComponent, Users
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
