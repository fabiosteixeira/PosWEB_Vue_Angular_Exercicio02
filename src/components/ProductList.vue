<template>
    <div>
        <div class="title">
            Lista de produtos (Product List)
        </div>
        <div>
            <ul id="postList">
            <li v-for="product in products" v-bind:key="product.id">
                <ProductItem
                    :product="product"
                />          
            </li>
            </ul>
        </div>
        <div class="total">
            Total de produtos na lista: <span>{{totalProducts}}</span>
        </div>
        <hr>
    </div>
</template>

<script>
import ProductItem from './ProductItem'
export default {
    name: 'ProductList',
    props: {
        products: Array
    },
    components: {
        ProductItem
    },
    computed: {
        totalProducts(){
            return this.products.length;
        }
    }
}
</script>

<style scoped>
  ul {
    list-style-type: none;
    margin: 10px;
    padding: 0px;
  }

  li{
    margin-bottom: 10px;
  }

  .total{
      text-align: right;
      margin-right: 20px;      
  }

  .total span {
      font-weight: 600;
      color: red;
  }
</style>