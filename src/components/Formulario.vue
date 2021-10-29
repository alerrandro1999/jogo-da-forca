<template>
    <div class="formulario">
        <div class="formulario-title"><h1>{{title}}</h1></div>
        <input type="text" class="formulario-input" v-model="inputValue">
        <button :disabled="inputValue.length === 0"
         v-on:click="onsubmit"
        >{{button}}</button>
    </div>
</template>

<script>
export default {
   name:'Formulario',
   props:{
       title: String,
       button: String,
       action: Function
   },
   data(){
       return{
           inputValue:''
       }
   },
   methods:{
       onsubmit: function () {
           this.action(this.inputValue);
           this.inputValue = '';
       }
   }
}
</script>

<style scoped>

    .formulario{
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        justify-content: center;
        margin-top: 20px;
    }

    .formulario-input{
        padding: 10px 5px;
        border: 0;
        border-radius: 5px;
        margin: 10px 0px;
        text-align: center;
        color: var(--color-text-dark);
        font-size: 16px;
    }
</style>