<template>
  <div id="ferramentas">
    <select v-model="caixaSel">
        <option value="" selected disabled>Selecione uma caixa</option>
        <option v-for="(caixa, index) in caixinhas" :key="index" :value="index">
            {{ caixa.titulo }}
            </option>
    </select>

    <div id="paleta">
        <div class="cor" :style="cor" v-for="(cor,index) in cores" :key="index" @click="alteraCor(cor)">

        </div>
    </div>

  </div>
</template>

<script>
export default {
    name: "ferramentas",
    props: ['caixinhas'],
    data: function() {
        return{
            cores: ['background: orange','background: blue','background: magenta'],
            caixaSel:''
        }
    }, methods: {
        alteraCor: function(cor){
            this.$emit('alteraCor', {
                cor: cor,
                caixa: this.caixaSel
            })
        }
    }
}
</script>

<style>
    #ferramentas{
        width: 380px;
        height: 230px;
        border: 1px solid #fff;
        margin: 5px auto 0px auto;
        padding: 10px;
    }
    #ferramentas select{
        width: 380px;
    }
    #paleta{
        width: 380px;
        height: 230px;
        display: flex;
    }
    .cor{
        width: 60px;
        height: 60px;
        border: 1px solid #fff;
        margin: 5px 3px 0 0;
        cursor: pointer;
    }
</style>