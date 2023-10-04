<script setup>
  const props = defineProps(["showResults"]);
</script>

<template>
    <div class="row">
      <h2 class="text-center my-4">{{props.showResults}}</h2>
    </div>
</template>