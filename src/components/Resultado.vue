<script setup>
    const props = defineProps(['number1', 'number2', 'result'])
</script>

<template>
    <span 
        v-if="props.number1 && props.number2 !=''"> 
            Resultado: {{ props.result }}
    </span>
    <span
        v-else-if="props.number1 || props.number2 === ''">
            Digite os números no campo acima
    </span>
</template>

<style scoped>
    span {
        font-weight: bold;        
    }
</style>