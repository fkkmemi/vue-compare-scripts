<template>
  <h3>option</h3>
  <TestOptionItem />
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import TestOptionItem from './TestOptionItem.vue'

export default defineComponent({
  name: 'TestOption',
  components: { TestOptionItem }
})
</script>
