<template>
  <div id="app">
    <img class="text-center" alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Catalogue /> 
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Catalogue from './components/Catalogue.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Catalogue
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif; 
  color: #2c3e50;
  margin-top: 60px;
}

img {
  display: block;
  margin: 0 auto
}

.container {
    width: 1200px;
    margin: 0 auto;  
}

.text-center {
  text-align: center;
}  
</style>
