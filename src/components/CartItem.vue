<template>
    <div>
        <p>
            {{item.name}}
            {{item.price}}.- Ft
            <button @click="$emit('remove-from-cart', item.id, item.price)">X</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "CartItem",
    props: ["item"]
}
</script>

<style scoped>

</style>