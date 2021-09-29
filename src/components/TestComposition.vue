<template>
  <h3>composition</h3>
  <TestCompositionItem />
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import TestCompositionItem from './TestCompositionItem.vue'

export default defineComponent({
  name: 'TestComposition',
  components: { TestCompositionItem },
  setup () {
    //
  }
})
</script>
