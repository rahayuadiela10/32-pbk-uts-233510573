<template>
  <div>
    <h2>Daftar Kegiatan</h2>
    <ul v-if="getTodosToShow.length > 0">
      <li
        v-for="(item, idx) in getTodosToShow"
        :key="idx"
      >
        {{ item.text }}
      </li>
    </ul>
    <p v-else>Tidak ada kegiatan yang terdaftar.</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const todoList = ref([
  { text: 'Belajar VueJS', completed: false },
  { text: 'Mengerjakan Tugas UTS', completed: true }
])

const getTodosToShow = computed(() => todoList.value)
</script>
