<script setup>
import { reactive } from 'vue';


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
    <header>
      <h1 class="mb-4">Calculadora VueJS</h1>
    </header>

    <form>
      <h2 class="mb-5">Digite os números e escolha a operação desejada</h2>
      <div class="row">

        <div class="col-md-5 mt-3">
          <input type="number" @keyup="evento => estado.numero1 = evento.target.value">
        </div>

        <div class="col-md-5 mt-3">
          <input type="number"  @keyup="evento => estado.numero2 = evento.target.value">
        </div>

        <div class="col-md-2">
                <select @change="evento => estado.filtro = evento.target.value" class="form-control">
                    <option value="---">--- ---</option>
                    <option value="adição">Adição</option>
                    <option value="subtração">Subtração</option>
                    <option value="multiplicação">Multiplicação</option>
                    <option value="divisão">Divisão</option>
                </select>
            </div>
      </div>
    </form>

    <h3 class="p-4 mt-2" v-if="estado.filtro === 'adição'"> O resultado da soma é  {{ soma() }}</h3>
    <h3 class="p-4 mt-2" v-else-if="estado.filtro === 'subtração'"> O resultado da subtração é  {{ subtracao() }}</h3>
    <h3 class="p-4 mt-2" v-else-if="estado.filtro === 'multiplicação'"> O resultado da multiplicação é  {{ multiplicação() }}</h3>
    <h3 class="p-4 mt-2" v-else-if="estado.filtro === 'divisão'"> O resultado da divisão é  {{ divisão() }}</h3>
    <h3 class="p-4 mt-2" v-else> Digite os números para o cálculo</h3>
  </div>
</template>

<style scoped>
  h1, h2, h3{
    color: #fff;
  };
</style>

