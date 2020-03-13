<template>
    <div>
        {{product.name}}: <span class="valor">{{this.formataValor(product.price)}}</span>
    </div>
</template>

<script>
export default {
    name: 'ProductList',
    props: {
        product: Object
    },
    methods: {
        formataValor(valor) {
            return new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(valor)
        }
    }
}

</script>

<style scoped>
    .valor {
        font-weight: 600;
        color: red;
    }
</style>