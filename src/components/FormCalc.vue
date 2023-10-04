<script setup>
  const props = defineProps(["numberOne", "numberTwo"])
</script>

<template>
    <div class="row">
    <div class="col">
      <form class="form-group">
      <label for="numberOne" class="pb-2">Insira o primeiro número:</label>
      <input required type="number" class="form-control pb-2" id="numberOne" @change="props.numberOne" value="0">
      <label for="numberTwo" class="pb-2">Insira o segundo número:</label>
      <input required type="number" class="form-control pb-2" id="numberTwo" @change="props.numberTwo" value="0">
    </form>
    </div>
  </div>
</template>