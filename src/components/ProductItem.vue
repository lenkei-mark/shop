<template>
    <div>
        <p>
            {{product.name}}
            {{product.price}}.- Ft
            <button @click="$emit('add-to-cart', product.id,  product.name, product.price)">Kosárba</button>
            <button @click="$emit('remove-from-products', product.id)">Törlés</button>
        </p>
    </div>
</template>

<script>

export default {
    name: "ProductItem",
    props: ["product"]
}
</script>

<style scoped>

</style>