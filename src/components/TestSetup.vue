<script setup lang="ts">
import { ref } from 'vue'
import TestItem from './TestSetupItem.vue'

const name = ref('abc')
const birth = ref(2000)
const add = () => { name.value += ' add' }
</script>
<template>
  <h3>setup</h3>
  <div>
    <input v-model="name" />
    <input v-model="birth" type="number" />
  </div>
  <div>
    <button @click="add">add</button>
  </div>
  <TestItem :name="name" :birth="birth" />
</template>
