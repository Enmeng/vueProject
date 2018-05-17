<template>
　　<div id="app">
　　　　<span v-bind:title="message">鼠标悬停</span>
　　</div>
</template>

<script>
import firstcomponent from './components/first-component.vue'
export default {
  name: 'app',
　　data () {
　　　　return {
　　　　　　message: 'Welcome to Your Vue.js App'
　　　　}
　　}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: green;
  margin-top: 60px;
}
</style>
