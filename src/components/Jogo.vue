<template>
    <div class="jogo">
        <Forca
            :erros="erros"
        />

        <Palavra 
            :palavra="palavra"
            :dica="dica"
            :verificaLetra="verificaLetra"
            :etapa="etapa"
        />

        <teclado 
            v-if="etapa === 'jogo'"
            :letras="letras"
            :verificaLetra="verificaLetra"
            :jogar="jogar"
        />

        <Final 
            v-if="etapa != 'jogo'"
            :etapa="etapa"
            :texto="etapa == 'ganhador' ? 'Parabéns' : 'Tadinho'"
            :jogarNovamente="jogarNovamente"
        />

    </div>
</template>

<script>

import Forca from './Forca'

import Palavra from './Palavra'

import Teclado from './Teclado'

import Final from './Final'




export default {
   name:'Jogo',
   props:{
     erros: Number,
     palavra: String,
     dica: String,
     verificaLetra: Function,
     etapa: String,
     letras: Array,
     jogar: Function,
     jogarNovamente:Function
   },
   data(){
       return{
     
       }
   },
   methods:{
     
   },
   components:{
       Forca,
       Palavra,
       Teclado,
       Final
   }
}
</script>

<style scoped>

    .jogo{
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
  
</style>