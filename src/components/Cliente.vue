<template>
<div id="cliente">
            <h4>Nome:{{nome}}</h4>
            <hr>
            <p>{{descricao}}</p>
            <hr>
            <p>Numero:{{numero}}</p>
            <p>Email:{{email}}</p>
            <p>Idade:{{idade}}</p>
  
</div> 
</template>
<script>
export default {
    data(){
            return{
                
                }

    },
    props:{
        nome:String,
        numero:String,
        email:String,
        idade:Number,
        descricao:String

    }
}
</script>

<style scoped>
div #cliente{
    background : linear-gradient(329.54deg,#76d6df 0%,#1bb1bf 100%);
    padding:1%;
    width: 300px;
    height: 250px;
    margin-top:1%;
}
</style>

