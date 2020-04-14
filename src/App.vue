<template>
  <div id="app">
    <caixas :caixinhas="caixinhas"/>
    <ferramentas :caixinhas="caixinhas" @alteraCor="alteraCor($event)"/>
  </div>
</template>

<script>
import caixas from "./caixas.vue"
import ferramentas from "./ferramentas.vue"

export default {
  name: 'App',
  components: {
    caixas,ferramentas
  }, data:function(){
    return{
      caixinhas:[{
        titulo: "1",
        cor: "background: yellow"
      },{
        titulo: "2",
        cor: "background: green"
      },{
        titulo: "3",
        cor: "background: red"
      }]
    }
  }, methods:{
    alteraCor: function(event){
      this.caixinhas[event.caixa].cor=event.cor      
    }
  }
}
</script>

<style>
</style>
