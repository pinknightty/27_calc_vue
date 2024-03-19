<script setup>
import { reactive } from 'vue';

const standyBy = reactive ({
  numeros: [
    {
      valorAtual: '000',
    }
  ]
 })

const operador = () => {
  const { operadorClicado } = numeros;
  let number1 = 0;
  let number2 = 0;
  switch (operadorClicado) {
    case 'soma':
      return number1 + number2;
    case 'subtrair':
      return number1 - number2;
    case 'multiplicar':
      return number1 * number2;
    case 'dividir': 
      return number1 / number2;

    default:
        return '';
  }
}

// @change="evento => standyBy.numeros = evento.target.value"
</script>

<template> 
 <div class="container">
  <header class="p-5 mb-4 mt-4 bg-info rounded-4">
  <h1>Calculadora com VueJS</h1>
</header>
</div>
<form>
  <div class="row">
    <div class="col-sm-3" id="left-space">
      <input class="form-control-sm" type="number" placeholder="Digite um número!">
    </div>
    <div class="col-sm-3">
      <input class="form-control-sm" type="number" placeholder="Digite outro número!">
    </div>
    <div class="col-md-2">
      <select class="form-control-sm">
        <option  id="soma" value="soma">Somar</option>
        <option id="subtrair" value="subtrair">Subtrair</option>
        <option id="multiplicar" value="multiplicar">Multiplicar</option>
        <option id="dividir" value="dividir">Dividir</option>
    </select>
    </div>
  </div>
</form>

<br/>
Resultado:
{{ operador ()}}

</template>


<style scoped>
  #left-space {
    margin-left: 16px;
}

#btn-space {
  padding-right: 8px;
}

</style>


