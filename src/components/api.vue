<script setup>
import {ref , onMounted } from 'vue'

const emit = defineEmits(['updateList'])
const handleClick = (user) => {
  emit('userClicked', user)
}

const list = ref([])
onMounted(async () => {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    const data = await res.json()
    list.value = data
  } catch (error) {
    console.error('Error fetching posts:', error)
  }
})
</script>

<template>
  <div>
    <h2>User List</h2>
    <ul>
      <li v-for="item in list" :key="item.id" @click="handleClick(item)">{{ item.name }}</li>
    </ul>
  </div>
</template>

<style>
</style>