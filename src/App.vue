<template>
  <div>
    <h1>
      <span>
        Antique’s
      </span>
    </h1>
    <chart :items="chartItems"/>
    <products @emit-product-to-app="addProd"/>
  </div>
</template>

<script>
import Products from './components/Products.vue';
import Chart from './components/Chart.vue';

export default {
  name: 'App',
  components: {
    Products,
    Chart
  },
  data() {
      return {
          chartItems: [],
      }
  },
  methods: {
    addProd: function(item) {
      this.chartItems.push(item);
    }
  }
}
</script>

<style>
html {
  background: #edf0f4;
}
body {
  font-family: 'Markazi Text', serif;
  color: #333;
}
h1 {
  text-align: center;
}
h1 span {
  display: inline-block;
  font-size: 3rem;
  font-weight: 400;
  color: #c77474;
  border: 3px solid #c77474;
  padding: 1.2rem 1.5rem;
  line-height: 0.6;
}
</style>
