<script setup>
    const props = defineProps(['operacao', 'number1', 'number2'])
</script>

<template>    
        <div class="operation">
         <h2>Selecione a operação</h2>
         <select @change="props.operacao">
            <option value="+">Soma</option>
            <option value="-">Subtração</option>
            <option value="*">Multiplicação</option>
            <option value="/">Divisão</option>
            <option value="^">Exponenciação</option>            
         </select>
    </div>
    <input class="form-control-sm" @keyup="props.number1" required type="number" placeholder="insira um número" />
    <input class="form-control-sm" @keyup="props.number2" required type="number" placeholder="insira um número" />
    
</template>

<style scoped>
    h2 {
        margin-top: 16px;
        margin-bottom: 32px;
    }

    input {
        display: block;
        margin: 32px;
        padding: 8px;
        border-radius: 4px;
    }

    select {
        margin-bottom: 16px;
    }

    .operation {
        display: block;
    }

</style>