<template>
  <div id="app">
      <h1>Estudos</h1>
      <Cliente nome="Gabriel" numero="2123123123" email="gab@.com" idade=20 descricao="dsadada"/>
      <Cliente  nome="Junior" numero="2321312331" email="dasda@a.com" idade=19 descricao="dasdasd"/>
      <Cliente  nome="José" numero="3123123312" email="sda@a.com" idade=18 descricao="dasdsada"/>
      <Cliente  nome="Marcio" numero="312312312" email="sa@as.com" idade=17 descricao="dasdasda"/>
      <Cliente  nome="Maria" numero="31231231112" email="mdsa@sa.com" idade=16 descricao="gdfsfas"/>
  </div>
</template>

<script>

import Cliente  from './components/Cliente'
export default {
  name: 'App',
  components:{
    Cliente 
  }
}
</script>

<style>
#app {
  background-color:lightblue ;
  padding:1%;
}
</style>
