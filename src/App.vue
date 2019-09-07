<template>
  <div id="app">
    <Products v-bind:products="products" v-on:add-to-cart="addToCart" v-on:remove-from-products="removeFromProducts"/>
    <Cart v-bind:cart="cart" v-on:remove-from-cart="removeFromCart"/>
    <h3>Ár: {{price}}.- Ft</h3>
    <AddProduct v-on:add-product="addProduct"/>
  </div>
</template>

<script>
import Products from './components/Products';
import Cart from './components/Cart';
import AddProduct from './components/AddProduct';

export default {
  name: 'app',
  components: {
    Products,
    Cart,
    AddProduct
  },
  data(){
    return{
      cart: [],
      price: 0,
      products: [
        {
          id:0,
          name: "Popcorn",
          price: 690
        },
        {
          id:1,
          name: "Nachos",
          price: 890
        },
        {
          id:2,
          name: "Cola",
          price: 390
        }
      ]
    }
  },
  methods:{
    addToCart(id, name, price){
      this.cart = [...this.cart, {id, name, price}];
      this.price+=price;
    },
    removeFromCart(id, price){
      for(let i = 0;i<this.cart.length;i++){
        if(this.cart[i].id==id){
          this.price-=this.cart[i].price;
          this.cart.splice(i,1);
          return;
        }
      }
    },
    addProduct(newProduct){
      this.products = [...this.products, newProduct];
    },
    removeFromProducts(id){
      for(let i = 0;i<this.products.length;i++){
        if(this.products[i].id==id){
          this.products.splice(i,1);
          return;
        }
      }
    }
  }
}
</script>

<style>
</style>
