<script setup>
    const props = defineProps(['adicao', 'subtracao', 'multiplicacao', 'divisao', 'somaFunction', 'subtracaoFunction', 'multiplicacaoFunction', 'divisaoFunction'])
</script>

<template>
    <h3 class="p-4 mt-2" v-if="props.adicao === 'adição'"> O resultado da soma é  {{ props.somaFunction }}</h3>
    <h3 class="p-4 mt-2" v-else-if="props.subtracao === 'subtração'"> O resultado da subtração é  {{ props.subtracaoFunction }}</h3>
    <h3 class="p-4 mt-2" v-else-if="props.multiplicacao === 'multiplicação'"> O resultado da multiplicação é  {{ props.multiplicacaoFunction }}</h3>
    <h3 class="p-4 mt-2" v-else-if="props.divisao === 'divisão'"> O resultado da divisão é  {{ props.divisaoFunction }}</h3>
    <h3 class="p-4 mt-2" v-else> Digite os números para o cálculo</h3>
</template>