<script lang="ts" setup>
import { ref } from 'vue'
import type { Ref } from 'vue'
import type { Iskills, Iteacher } from 'types/types.ts'
/**
 * Formulario para datos de docente
 *
 * Skills
 * Nombre
 * Apellido Materno
 * Apellido Paterno
 * Rut
 * Materias
 */

// Reactive Variables
const skills: Ref<Array<Iskills>> = ref([
  { code: 'mat', name: 'Matemáticas' },
  { code: 'prog', name: 'Programación' },
  { code: 'db', name: 'Bases de datos' },
  { code: 'fe', name: 'Front End' },
  { code: 'sass', name: 'Sass' }
])

const selectedOption = ref(null) // this is the selected variable by form
const name: Ref<string> = ref('')
const lastName1: Ref<string> = ref('')
const lastName2: Ref<string> = ref('')
const rut: Ref<string> = ref('')

const emit = defineEmits(['newRow'])
const handleSubmit = async () => {
  const data: Iteacher = {
    name: name.value,
    lastName1: lastName1.value,
    lastName2: lastName2.value,
    rut: rut.value,
    skills: selectedOption.value
  }
  emit('newRow', data)
}
</script>

<template>
  <h2>Datos profesor</h2>
  <form @submit.prevent="handleSubmit">
    <div class="form-check">
      <label for="nombre">Nombre</label>
      <input type="text" id="nombre" v-model="name" />
    </div>

    <div class="form-check">
      <label for="apellido1">Apellido Paterno</label>
      <input type="text" id="apellido1" v-model="lastName1" />
    </div>

    <div class="form-check">
      <label for="apellido2">Apellido Materno</label>
      <input type="text" id="apellido2" v-model="lastName2" />
    </div>

    <div class="form-check">
      <label for="rut">Rut</label>
      <input type="text" id="rut" v-model="rut" />
    </div>

    <div class="form-check">
      <label for="skills">Habilidades/skills</label>
      <select id="skills" name="skills" v-model="selectedOption">
        <option v-for="skill in skills" :value="skill.code" :key="skill.code">
          {{ skill.name }}
        </option>
      </select>
    </div>

    <button type="submit">Submit</button>
  </form>
</template>

<style scoped></style>
