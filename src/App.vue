<template>
  <div id="app">
      <h1>Estudos</h1>
      <Cliente/>
      <Produto/>
  </div>
</template>

<script>

import Cliente  from './components/Cliente'
import Produto from './components/Produto'
export default {
  name: 'App',
  components:{
    Cliente,Produto 
  }
}
</script>

<style>
#app {
  
}
</style>
