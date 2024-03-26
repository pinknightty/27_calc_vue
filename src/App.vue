<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';

import Operacao from './components/Operacao.vue';
import Resultado from './components/Resultado.vue';
import Cabecalho from './components/Cabecalho.vue';

const standyBy = reactive ({
  operation: '+',
    number1: '',
    number2: '',
 })

 const resultado = () => {
  const {operation} = standyBy
  switch(operation) {
    case '-':
      return parseFloat(standyBy.number1) - parseFloat(standyBy.number2)
    case '*':
      return parseFloat(standyBy.number1) * parseFloat(standyBy.number2)
    case '/':
      return parseFloat(standyBy.number1) / parseFloat(standyBy.number2)
    case '^':
      return parseFloat(standyBy.number1) ** parseFloat(standyBy.number2)   
    default:
      return parseFloat(standyBy.number1) + parseFloat(standyBy.number2)
  }
 }
</script>

<template> 
  <div class="container"><
    <Cabecalho />
    <Operacao :operacao="evento=> standyBy.operation = evento.target.value"
       :number1="evento => standyBy.number1 = evento.target.value"
       :number2="evento => standyBy.number2 = evento.target.value" />
    <Resultado 
      :number1="standyBy.number1" 
      :number2="standyBy.number2"
      :result="resultado()"/>
  </div>

</template>


<style scoped>
  #left-space {
    margin-left: 16px;
}

#btn-space {
  padding-right: 8px;
}

</style>