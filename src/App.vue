<template>
  <div id="app">
    <ProductList
      :products="products"
    />
    <ProductForm
      :addProduct="addProduct"
    />
  </div>
</template>

<script>

import ProductList from './components/ProductList'
import ProductForm from './components/ProductForm'

export default {
  name: 'App',
  data(){
      return {
        products: [
          { 
            id: 1
            , name: "Echo Dot (3ª Geração): Smart Speaker com Alexa - Cor Preta"
            , category: "Tecnologia"
            , price: 249.00
          },
          { 
            id: 2
            , name: "Cafeteira Nuova Moka Express 6 Xicaras Bialetti"
            , category: "Cozinha"
            , price: 146.00
          },
          { 
            id: 3
            , name: "Patinete Scooter Azul/rosa Little Tikes Little Tikes Azul"
            , category: "Infantil"
            , price: 297.00
          }
        ]
      } 
  },
  components: {
    ProductList,
    ProductForm
  },
  methods: {
    addProduct(product){
      this.products = this.products.concat({
        name: product.name,
        category: product.category,
        price: product.price
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
