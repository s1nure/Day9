<template>
  <div>
    <table class="w-full border-3 text-left text- bg-slate-300">
      <thead class="border-b">
        <tr>
          <th>Name</th>
          <th>group</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student, index in students" :key="index">
          <td>{{ student.name }}</td>
          <td>{{ student.group }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'
const students = ref([])

onMounted(()=>{
  axios
  .get('http://34.82.81.113:3000/students')
  .then((response)=>{
    students.value = response.data
  })
})
</script >
