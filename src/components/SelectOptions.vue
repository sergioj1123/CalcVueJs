<script setup>
  const props = defineProps(["operationType"]);
</script>

<template>
        <div class="row text-center m-star-4">
      <div class="col m-4">
        <select class="form-control text-center" @change="props.operationType">
        <option value="sum">Soma</option>
        <option value="subtraction">Subtração</option>
        <option value="mult">Multiplicação</option>
        <option value="div">Divisão</option>
      </select>
      </div>
    </div>
</template>