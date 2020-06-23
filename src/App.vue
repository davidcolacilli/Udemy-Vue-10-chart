<!-- 
# Alistar el proyecto
# Crear el componente Producto
# Mostrar los productos
# Crear el componente carrito
# Agregar productos al carrito
# Desactivar el botón de agregar al carrito
# Eliminar productos del carrito
# Mostrar el total a pagar
-->
<template>
  <div>
    <h1>
      <span>
        Antique’s
      </span>
    </h1>
    <div class="wrapper">
      <products @emit-product-to-app="addProd"/>
      <chart :items="chartItems"/>
    </div>
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
  width: 74rem;
  margin: 3rem auto 2rem;
}
h1 span {
  display: inline-block;
  font-size: 3rem;
  font-weight: 400;
  color: #c77474;
  border: 3px solid #c77474;
  padding: 1.3rem;
  line-height: 0.6;
}
.wrapper {
  display: flex;
}
</style>
