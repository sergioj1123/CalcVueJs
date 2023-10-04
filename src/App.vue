<script setup>
  import { reactive } from 'vue';
  import FormCalc from "./components/FormCalc.vue"
  import SelectOptions from "./components/SelectOptions.vue"
  import Results from "./components/Results.vue"

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
    <FormCalc :numberOne="event=>state.numberOne=event.target.value" :numberTwo="event=>state.numberTwo=event.target.value"></FormCalc>
    <SelectOptions :operationType="event=>state.operationType=event.target.value"></SelectOptions>
    <Results :showResults="showResult()"></Results>
  </div>
</template>

<style scoped>

</style>
