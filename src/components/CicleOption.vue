<template>
  <h2>Hola Mundo</h2>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CicleOption',
  data() {},
  methods: {},
  created() {
    console.log('Created Component', this)
  },
  mounted() {
    console.log('Mounted Component', this)
  },
  updated() {
    console.log('Updated Component', this)
  },
  unmounted() {
    console.log('Unmounted Component', this)
  }
})
</script>
