<template>
    <aside>
        <i>{{items.length}}</i>
        <ul v-if="items.length">
            <li v-for="item in items" :key="item.id">
                <p>{{item.name}}: {{item.price}}</p>
                <button @click="removeItem(item)">Remove</button>
            </li>
        </ul>
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
            }
        }

    }
}
</script>
<style lang="stylus" scoped>

</style>