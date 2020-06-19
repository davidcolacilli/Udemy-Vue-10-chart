<template>
    <article>
        <product v-for="product in products" :key="product.id" :product="product"/>
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
            products: products,
        }
    }
}
</script>
<style scoped>
article {display: flex; flex-direction: row; flex-wrap: wrap;}
</style>