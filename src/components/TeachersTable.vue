<script lang="ts" setup>
import TeacherForm from './TeacherForm.vue'
import { ref } from 'vue'
import type { Ref } from 'vue'
// interfaces
interface ITeacher {
  name: string
  lastName1: string
  lastName2: string
  rut: string
  skills: string
}

// Reactive Variables
let teacherRows: Ref<Array<ITeacher>> = ref([])

function setNewRow(data: ITeacher): void {
  teacherRows.value.push(data)
}
</script>

<template>
  <TeacherForm @newRow="setNewRow" />

  <h2>Profesores Registrados</h2>
  <table>
    <thead>
      <th>N°</th>
      <th>Nombre</th>
      <th>Apellido Paterno</th>
      <th>Apellido Materno</th>
      <th>Rut</th>
      <th>Materias</th>
    </thead>
    <tbody>
      <tr v-for="teacher in teacherRows" :key="teacher.rut">
        <td></td>
        <td>{{ teacher.name }}</td>
        <td>{{ teacher.lastName1 }}</td>
        <td>{{ teacher.lastName2 }}</td>
        <td>{{ teacher.rut }}</td>
        <td>{{ teacher.skills }}</td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped></style>
