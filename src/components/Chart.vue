<template>
    <aside>
        <h3>
            <span>{{items.length}} items in chart</span>
            <span>Total: ${{total()}}</span>
        </h3>
        <ul v-if="items.length">
            <li v-for="item in items" :key="item.id">
                <p>{{item.name}} <span>${{Number(item.price).toFixed()}}</span></p>
                <button @click="removeItem(item)" class="btn-link">Remove</button>
            </li>
        </ul>
        <button @click="checkout()" v-if="items.length" class="btn btn-action">Checkout</button>
    </aside>
</template>
<script>
export default {
    name: 'Chart',
    props: {
        items: Array
    },
    methods: {
        removeItem: function(item) {
            let i = this.items.indexOf(item);
 
            if ( i !== -1 ) {
                this.items.splice( i, 1 );
                item.amount++;
            }
        },
        /* REFACTOR - NOT WORKING YET
        removeItem: function(item) {
            this.items = this.items.filter(i => i.id !== item.id);
        }, */
        total: function() {
            return this.items.reduce((counter, item) => counter + Number(item.price), 0)
        },
        /* total: function() {
            let tot = 0;

            for(let it of this.items) {
                tot = tot + Number(it.price);
            }
            return tot;
        } */
        checkout: function() {
            this.$emit("checkout");
        }
    }
}
</script>
<style scoped>
aside {
    border-left: 1px solid #ccc;
    padding: 1rem;
    min-width: 16rem;
}
h3 {
    margin-top: 0;
    display: flex;
    justify-content: space-between;
}
p span {
    display: block;
    color: #777;
}
ul {
    list-style-type: none;
    padding:0;
}
li {
    border-top: 1px solid #CCC;
    display: flex;
    justify-content: space-between;
}
li:first-child {
    border: none;
}

</style>