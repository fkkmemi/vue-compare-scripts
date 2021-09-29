<template>
  <h3>composition</h3>
  <div>
    <input v-model="name" />
    <input v-model="birth" type="number" />
  </div>
  <div>
    <button @click="add">add</button>
  </div>
  <TestItem :name="name" :birth="birth" />
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import TestItem from './TestCompositionItem.vue'

export default defineComponent({
  name: 'TestComposition',
  components: { TestItem },
  setup () {
    const name = ref('abc')
    const birth = ref(2000)
    const add = () => { name.value += ' add' }
    return { name, birth, add }
  }
})
</script>
