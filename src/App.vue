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
      <chart :items="chartItems" @checkout="checkout"/>
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
    },
    checkout() {
      this.chartItems = [];
      alert("Success");
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
button:focus {
    outline: none;
}
button:disabled {
    opacity: .4;
    background: none;
}
.btn-link {
    display: inline-block;
    text-transform: uppercase;
    background: none;
    color: #c77474;
    border: none;
    font-size: .5rem;
}
.btn-link:hover {
    color: #853939;
}
.btn {
    display: block;
    width: 100%;
    border: 1px solid #c77474;
    text-transform: uppercase;
    text-align: center;
    padding: 1rem;
    margin-top: 0.9rem;
    border-radius: 3px;
    background: none;
    color: #c77474;
}
.btn:hover {
    background: rgba(199, 116, 116, .1);
}
.btn:focus:not(:disabled) {
    border: 1px solid #8f5555;
}
.btn-action {
  background: #c77474;
  border: none;
  color: #FFF;
}
.btn-action:hover {
  background: #8f5555;
}
</style>
