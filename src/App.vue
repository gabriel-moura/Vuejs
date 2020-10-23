<template>
  <div id="app">
    <h1>Estudos</h1>
      <input type="text" placeholder="Nome" v-model="nomeField">
      <br>
      <input type="text" placeholder="E-mail" v-model="emailField">
      <br>
      <input type="number" placeholder="idade" v-model="idadeField">
      <br>
      
      <button @click="cadastrarUsuario">Cadastrar</button>
 <div v-for="(cliente,index) in clientes" :key="cliente.id"> 
   <h4>{{index+1}}</h4>
   
   <Cliente
      :cliente="cliente" 
    />
    
 </div>
  </div>
</template>

<script>

import Cliente  from './components/Cliente'
export default {
  name: 'App',
  data(){
    return{
           
       nomeField: "",
       emailField:"",
       idadeField:0,
      clientes: [
        {
          id:22,
          nome: "Gabriel",
          email: "gabriel@email.com",
          idade: 22
        },
        {
           id:23,
          nome: "Lucas",
          email: "gabriel@email.com",
          idade: 20
        },
        {
           id:24,
          nome: "Renan",
          email: "gabriel@email.com",
          idade: 21

        },


              
            ],
        
         
    }
  },
  components:{
    Cliente
  },
   methods:{
          cadastrarUsuario: function(){

            if()
              this.clientes.push({nome:this.nomeField, email:this.emailField, idade:this.idadeField, id:Date.now()})
              this.nomeField = "";
              this.emailField = "";
              this.idadeField= 0
          }
        }
             
}
</script>

<style>
#app {
  background-color: lightblue;
  padding: 1%;
}
</style>
