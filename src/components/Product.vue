<template>
    <section>
        <img :src="product.image" :alt="product.name" width="200">
        <h4>${{product.price}}</h4>
        <h3>{{product.name}}</h3>
    </section>    
</template>
<script>
export default {
    name: 'Product',
    props: {
        product: Object
    }
}
</script>
<style scoped>
section {
    margin: 1rem; 
    padding: 1rem; 
    /* border: 1px solid #eee; */
    box-shadow: 0 1px 1px rgba(0,0,0,0.2);
}
img {margin: -1rem -1rem 0;}
h4 {
    margin: 0;
    font-size: 1.6rem;
    font-weight: 400;
}
h3 {
    margin: 0;
    font-size: 1.2rem;
    font-weight: 400;
    color: #777;
}
</style>