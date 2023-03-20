<script setup>
    const props = defineProps(['num1', 'num2', 'trocarFiltro'])
</script>

<template>
    <form>
        <h2 class="mb-5">Digite os números e escolha a operação desejada</h2>
        <div class="row">

            <div class="col-md-5 mt-3">
                <input type="number" @keyup="props.num1">
            </div>

            <div class="col-md-5 mt-3">
                <input type="number" @keyup="props.num2">
            </div>

            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value="---">--- ---</option>
                    <option value="adição">Adição</option>
                    <option value="subtração">Subtração</option>
                    <option value="multiplicação">Multiplicação</option>
                    <option value="divisão">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
    h2 {
        color: #fff;
    }
</style>