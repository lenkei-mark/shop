<template>
    <div>
        <h1>Termék hozzáadása</h1>
        <form @submit="addProduct">
            <input type="text" v-model="name" name="name" placeholder="Termék neve">
            <input type="number" v-model="price" name="price" placeholder="Termék ára">
            <input type="submit" value="Hozzáadás">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';

export default {
    name: "AddProduct",
    data(){
        return{
            name: '',
            price: '',
        }
    },
    methods:{
        addProduct(e){
            e.preventDefault();
            const newProduct = {
                id: uuid.v4(),
                name: this.name,
                price:  parseInt(this.price)
            }
            this.$emit('add-product', newProduct);
            this.name='';
            this.price='';
        }
    }
}
</script>

<style scoped>

</style>