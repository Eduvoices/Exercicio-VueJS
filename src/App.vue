<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Header.vue';
import Formulario from './components/Form.vue';
import Resultado from './components/Resultado.vue';


  const estado = reactive({
    numero1: 0,
    numero2: 0,
    filtro: '---'
  })

  function soma(){
    const {numero1, numero2} = estado

    return +numero1 + +numero2
  }

  function subtracao(){
    const {numero1, numero2} = estado
    return +numero1 - +numero2
  }

    function multiplicação(){
    const {numero1, numero2} = estado
    return +numero1 * +numero2
  }

    function divisão(){
    const {numero1, numero2} = estado
    return numero1 / numero2
  }

</script>

<template>
  <div class="container p-5 mb-4 mt-5 bg-info rounded-3">
    <Cabecalho />
    <Formulario :num1="evento => estado.numero1 = evento.target.value" :num2="evento => estado.numero2 = evento.target.value" :trocar-filtro="evento => estado.filtro = evento.target.value"/>
    <Resultado :adicao="estado.filtro" :subtracao="estado.filtro" :multiplicacao="estado.filtro" :divisao="estado.filtro" :soma-function="soma()" :subtracao-function="subtracao()" :multiplicacao-function="multiplicação()" :divisao-function="divisão()"/>
  </div>
</template>

<style scoped>
  h2, h3{
    color: #fff;
  };
</style>

