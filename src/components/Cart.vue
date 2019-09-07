<template>
    <div>
        <h1>Kosár</h1>
        <div v-bind:key="index" v-for="(item, index) in cart">
            <CartItem v-bind:item="item" v-on:remove-from-cart="$emit('remove-from-cart', item.id, item.price)"/>
        </div>
        <h3>Ár: {{price}}.- Ft</h3>
    </div>
</template>

<script>
import CartItem from './CartItem';

export default {
    name: "Cart",
    components: {
        CartItem
    },
    props: ["cart", "price"]
}
</script>

<style scoped>

div{
    background-color: #DB4437;
    color: #F3F3F4;
}

h3{
    padding-bottom:10px;
}

</style>