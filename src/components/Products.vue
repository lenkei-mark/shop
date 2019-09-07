<template>
    <div>
        <h1>Termékek</h1>
        <div v-bind:key="index" v-for="(product, index) in products">
            <ProductItem v-bind:product="product" 
            v-on:add-to-cart="$emit('add-to-cart', product.id, product.name, product.price)"
            v-on:remove-from-products="$emit('remove-from-products', product.id)"/>
        </div>
    </div>
</template>

<script>
import ProductItem from './ProductItem'

export default {
    name: "Products",
    components:{
        ProductItem
    },
    props: ["products"]
}
</script>

<style scoped>

</style>