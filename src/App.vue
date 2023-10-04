<script setup>
  import { reactive } from 'vue';

  const state = reactive({
      numberOne: 0,
      numberTwo: 0,
      operationType: "sum",
  })

  const sum = () => {
    return (parseInt(state.numberOne) + parseInt(state.numberTwo))
  }

  const sub = () => {
    return (parseInt(state.numberOne) - parseInt(state.numberTwo))
  }

  const div = () => {
    return (parseInt(state.numberOne) / parseInt(state.numberTwo))
  }

  const mult = () => {
    return (parseInt(state.numberOne) * parseInt(state.numberTwo))
  }

  const showResult = () =>{
    const {operationType} = state
    switch (operationType){
      case "sum": return sum()
      case "subtraction": return sub()
      case "mult": return mult()
      case "div": return div()
    }
  }

</script>

<template>
  <div class="container">
    <h1 class="text-center py-4"> Calculadora</h1>
    <div class="row">
      <div class="col">
        <form class="form-group">
        <label for="numberOne" class="pb-2">Insira o primeiro número:</label>
        <input required type="number" class="form-control pb-2" id="numberOne" @change="event=>state.numberOne=event.target.value" value="0">
        <label for="numberTwo" class="pb-2">Insira o segundo número:</label>
        <input required type="number" class="form-control pb-2" id="numberTwo" @change="event=>state.numberTwo=event.target.value">
      </form>
      </div>
    </div>
    <div class="row text-center m-star-4">
      <div class="col m-4">
        <select class="form-control text-center" @change="event=>state.operationType=event.target.value">
        <option value="sum">Soma</option>
        <option value="subtraction">Subtração</option>
        <option value="mult">Multiplicação</option>
        <option value="div">Divisão</option>
      </select>
      </div>
    </div>
    <div class="row">
      <h2 class="text-center my-4">{{showResult()}}</h2>
    </div>
  </div>
</template>

<style scoped>

</style>
