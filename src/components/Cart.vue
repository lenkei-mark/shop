<template>
    <div>
        <h1>Kosár</h1>
        <div v-bind:key="index" v-for="(item, index) in cart">
            <CartItem v-bind:item="item" v-on:remove-from-cart="$emit('remove-from-cart', item.id, item.price)"/>
        </div>
    </div>
</template>

<script>
import CartItem from './CartItem';

export default {
    name: "Cart",
    components: {
        CartItem
    },
    props: ["cart"]
}
</script>

<style scoped>

</style>