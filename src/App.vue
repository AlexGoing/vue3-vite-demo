<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Hello Vue 3.0 + Vite" /> -->
  <div>
    <count title="vue333333"></count>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import count from './components/count.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    count
  }
}
</script>
