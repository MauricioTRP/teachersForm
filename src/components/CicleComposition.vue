<template>
  <h2>Composition Cicle</h2>
</template>

<script lang="ts">
import { onBeforeMount, onUpdated } from 'vue'

onBeforeMount(() => {
  /** Se usa un callback dentro del hook */
  console.log('Before Mount')
})

onUpdated(() => {
  console.log('On updated')
})
</script>

<style scoped></style>
