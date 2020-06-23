<template>
    <section>
        <img :src="product.image" :alt="product.name">
        <h4>${{Number(product.price).toFixed()}}</h4>
        <h3>{{product.name}}</h3>
        <button @click="addProduct(product)" :disabled="!product.amount">Add</button>
    </section>    
</template>
<script>
export default {
    name: 'Product',
    props: {
        product: Object
    },
    methods: {
        addProduct(product) {
            this.$emit('emit-product-to-products', product);
        }
    }
}
</script>
<style scoped>
section {
    margin: 1rem; 
    padding: 1rem;
    box-shadow: 0 1px 1px rgba(0,0,0,0.2);
    width: 10.5rem;
    background: #FFF;
    border-radius: 2px;
    overflow: hidden;
}
img {width: 12.5rem; margin: -1rem -1rem 0;}
h4 {
    margin: 0;
    font-size: 1.6rem;
    font-weight: 400;
    color: #c77474;
}
h3 {
    margin: 0;
    font-size: 1.2rem;
    font-weight: 400;
    color: #777;
}
button {
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
button:hover {
    background: rgba(199, 116, 116, .1);
}
button:focus {
    outline: none;
}
button:focus:not(:disabled) {
    border: 1px solid #8f5555;
}
button:disabled {
    opacity: .4;
    background: none;
}
</style>