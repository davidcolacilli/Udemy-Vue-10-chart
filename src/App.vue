<template>
  <div>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1>Antique’s</h1>
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
h1 {
  font-size: 4rem;
  font-weight: 900;
  text-align: center;
}
</style>
