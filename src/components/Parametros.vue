<template>
    <Painel titulo="Parâmetros" vermelho>
        <div class="parametros">
            <span>
                <strong>Quantidade Padrão: </strong> 
                <input type="number" v-model="quantidade">
            </span>
            <span>
                <strong>Preço Padrão: </strong>
                <input type="number" v-model="preco">
            </span>
        </div>
    </Painel>
</template>

<script>
export default {
    computed: {
        quantidade: {
            //lê o valor
            get(){
                return this.$store.state.parametros.quantidade
            },
            //atualizar o valor
            set(valor) {
                this.$store.commit('setQuantidade', valor)
            }
        }, 
        preco: {
             //lê o valor
            get(){
                return this.$store.state.parametros.preco
            },
            //atualizar o valor
            set(valor) {
                this.$store.commit('setPreco', valor)
            }
        }
    },
}
</script>

<style>
    .parametros {
        display: flex;
        justify-content: space-around;
    }
</style>
