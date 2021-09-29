<template>
  <h3>option</h3>
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
import { defineComponent } from 'vue'
import TestItem from './TestOptionItem.vue'

export default defineComponent({
  name: 'TestOption',
  components: { TestItem },
  data () {
    return {
      name: 'abc',
      birth: 2000
    }
  },
  methods: {
    add () {
      this.name += ' add'
    }
  }
})
</script>
