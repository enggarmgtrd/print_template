<template>
  <div id="app">
    <packingBySerial />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import packingBySerial from './components/packingBySerial.vue'

export default {
  name: 'App',
  components: {
    packingBySerial
  }
}
</script>

<style>
html{
  font-size: 62.5%;
}
 #app{
   padding: 2rem;
 }
</style>
