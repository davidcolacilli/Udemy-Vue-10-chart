<template>
  <div>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <products/>
  </div>
</template>

<script>
/* import HelloWorld from './components/HelloWorld.vue' */
import Products from './components/Products'

export default {
  name: 'App',
  components: {
    Products
    /* HelloWorld */
  }
}
</script>

<style>
body {
  font-family: 'Markazi Text', serif;
  color: #333;
}
</style>
