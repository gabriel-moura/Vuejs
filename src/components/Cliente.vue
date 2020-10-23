<template>
<div :class="{'cliente':!isPremium,'clientePremium':isPremium}">
            <h4>Nome:{{cliente.nome}}</h4>
            <hr>
            <p>Email:{{cliente.email}}</p>
            <p> Idade:{{cliente.idade}}</p>
            <button @click="changeColor">Clique aqui</button>
  
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

