<script setup>
import { reactive } from 'vue';

const standyBy = reactive ({
    number1: 0,
    number2: 0,
 })


 function somar() {
   standyBy.number1 + standyBy.number2;
 }

 function subtrair() {
    standyBy.number1 - standyBy.number2;
 }

 function multiplicar() {
   standyBy.number1 * standyBy.number2;
 }

 function dividir() {
   standyBy.number1 / standyBy.number2;
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
      <select @change="reactive()" class="form-control-sm">
        <option value="Operação">Escolher operação</option>
        <option @click="somar" value="soma">Somar</option>
        <option @click="subtrair" id="subtrair" value="subtrair">Subtrair</option>
        <option @click="multiplicar" id="multiplicar" value="multiplicar">Multiplicar</option>
        <option @click="dividir" id="dividir" value="dividir">Dividir</option>
    </select>
    </div>
  </div>
</form>

<br/>
  <p>
    Resultado:  {{ somar() || subtrair() || multiplicar() || dividir ()}}
  </p>
</template>


<style scoped>
  #left-space {
    margin-left: 16px;
}

#btn-space {
  padding-right: 8px;
}

</style>


