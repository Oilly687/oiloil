<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome WU.ac.th"/>
  <HelloWorld msg1="Apaporn Thipsavak"/>
    <button @click="counter += 1">Add 1</button>
    <p>The button above has been clicked {{ counter }} times.</p> 
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      counter: 0
    }
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
