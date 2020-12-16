<template>
  <div id="app">
    
    <!-- <header id="headerapp">
    
       <a href="#">  
            <img id="logo" src="../src/assets/logoheader.png" alt="nao rolou">
        </a>
    
      
          <input type="text" id="inputstyle">

         
  </header> -->
<!-- <Home/> -->
  
    <h1>Estudos</h1>
    <small id="nomeErro" v-show="deuErro"
      >O nome é invalido, tente novamente</small
    ><br />
    <input type="text" placeholder="Nome" v-model="nomeField" />
    <br />
    <input type="text" placeholder="E-mail" v-model="emailField" />
    <br />
    <input type="number" placeholder="idade" v-model="idadeField" />
    <br />

    <button @click="cadastrarUsuario">Cadastrar</button>
    <div v-for="(cliente, index) in orderElements" :key="cliente.id">
      <h4>{{ index + 1 }}</h4>

      <Cliente :cliente="cliente" @meDelete="escutandoEmissao($event)"/>
    </div> 
    
  </div>
</template>

<script>
import _ from 'lodash';
import Cliente from "./components/Cliente";
// import Home from "./components/Home";
export default {
  name: "App",
  data() {
    return {
      deuErro: false,
      nomeField: "",
      emailField: "",
      idadeField: 0,
      clientes: [
        {
          id: 22,
          nome: "Gabriel",
          email: "gabriel@email.com",
          idade: 22,
        },
        {
          id: 23,
          nome: "Lucas",
          email: "gabriel@email.com",
          idade: 20,
        },
        {
          id: 24,
          nome: "Renan",
          email: "gabriel@email.com",
          idade: 21,
        },
      ],
    };
  },
  components: {
    Cliente
// Home  
  },
  methods: {
    cadastrarUsuario: function() {
      if (
        this.nomeField == "" ||
        this.nomeField == " " ||
        this.nomeField.length < 3
      ) {
        this.deuErro = true;
      } else {
        this.deuErro = false;
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now(),
        });
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = 0;
      }
    },escutandoEmissao: function($event){
      console.log('evento recebido')
      var id = $event.idDoCliente
      var listaClientes=  this.clientes.filter(cliente => cliente.id != id)
      this.clientes = listaClientes

    }
  },
  computed:{
    orderElements: function(){
        return _.orderBy(this.clientes,['nome'],['asc']);
    }
  }
};
</script>

<style>
#nomeErro {
  color: red;
}
#headerapp{
display: flex;
align-items: center;
height:8vh;
width:100vw; 
background-color:aqua;
position: fixed;
top: 0;
left: 0;
}

#logo{
height: 8vh;
padding-left:3vw;
}
#inputstyle{
position: absolute;
left:250px;
height: 4vh;
width:60vw;
border-radius:5px; 
}
</style>
