<template>
    <div class="container">
        <div class="alert" v-if="isNameLimitExceeded">O nome do usuário não pode ultrapassar 15 caracteres!</div>
        <div class="title">
            Cadastrar novos produtos (Product Form)
        </div>
        <div class="divForm">
            <form @submit="onFormSubmit">
                <div>
                    <label>Nome: </label>
                    <input type="text" v-model="name">
                </div>
                <div>
                    <label>Categoria: </label>
                    <input type="text" v-model="category">
                </div>
                <div>
                    <label>Preço: </label>
                    <input type="number" step=".01" v-model="price">
                </div>
                <div>
                    <button type="submit">Cadastrar</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductForm',
    data() {
        return {
            name: "",
            category: "",
            price: "",
            isNameLimitExceeded: false
        }
    },
    props: {
        addProduct: Function
    },
    methods: {
        onFormSubmit(e) {
            e.preventDefault();
            this.addProduct({
                name: this.name,
                category: this.category,
                price: this.price
            });
        }
    },
    watch: {
        name(){
            if (this.name.length > 15) {
                this.isNameLimitExceeded = true
            } else {
                this.isNameLimitExceeded = false
            }
        }
    }
}
</script>

<style scoped>
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;        
    }

    .divForm{
        max-width: 400px;
        min-width: 300px;   
    }

    .divForm form{
        display: flex;
        flex-direction: column;
        align-items: flex-end;
    }

    form input {
        width: 200px;
    }

    .alert{
        color: red;
        margin-bottom: 20px;
    }
</style>