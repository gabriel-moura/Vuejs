<template>
<div :class="{'cliente':!isPremium,'clientePremium':isPremium}">
            <h4>Nome:{{cliente.nome}}</h4>
            <hr>
            <p>Email:{{cliente.email | caps}}</p>
            <p> Idade:{{cliente.idade}}</p>
            <button @click="changeColor">Clique aqui</button>
            <button @click="emitirEvento">Deletar</button>
            <h4>idEspecial: {{idEspecial}}</h4>
</div> 
</template>
<script>
export default {
    data(){
            return{
                isPremium: false
                }

    },
    props:{
        cliente: Object,
        showAge: Boolean

    },
    methods: {

            changeColor : function(){
                this.isPremium = !this.isPremium
            },
            emitirEvento: function(){
                console.log('Deletado')
                this.$emit("meDelete",{
                   idDoCliente: this.cliente.id ,nome:"gabriel", emPromocao:true, component: this
                })
            
            }

    },
     filters:{
        caps: function(value){
                return value.toUpperCase()
        }
    },
    computed:{
        idEspecial: function(){
            return (this.cliente.email + this.cliente.nome + this.cliente.id).toUpperCase() 
        }
    }
}
</script>

<style scoped>
.cliente{
    background : linear-gradient(329.54deg,#76d6df 0%,#1bb1bf 100%);
    padding:1%;
    width: 300px;
    height: 300px;
    margin-top:1%;
}
.clientePremium{
    background : linear-gradient(329.54deg,#ae9b0a 0%,#e8d909 100%);
    padding:1%;
    width: 300px;
    height: 300px;
    margin-top:1%;
}
</style>

