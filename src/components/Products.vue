<template>
  <div><Product v-for="product in products" :key="product.id" :products="product">{{ products }}</Product></div>
</template>

<script>
import productArr from "../../products.json";
import Product from "./Product.vue";

export default {
  name: "Products",
  data: function (){
   return{
     products: []
   }
  },
  created() {
    this.products = productArr
  },
  components: {
    Product
  }
}
</script>

<style scoped>

</style>