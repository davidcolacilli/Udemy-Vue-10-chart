<template>
    <article>
        <product v-for="product in products" :key="product.id" :product="product" @emit-product-to-products="addProduct"/>
    </article>    
</template>
<script>
import products from '../products.json';
import Product from './Product.vue';

export default {
    name: 'Products',
    components: {
        Product
    },
    data() {
        return {
            products
        }
    },
    methods: {
        addProduct(product) {
            this.$emit('emit-product-to-app', product);
        }
    }
}
</script>
<style scoped>
article {display: flex; flex-direction: row; flex-wrap: wrap; width: 58rem;
  margin: 0 auto;}
</style>