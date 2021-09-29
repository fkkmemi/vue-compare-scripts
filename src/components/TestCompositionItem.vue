<template>
  <h5>
    TestCompositionItem
  </h5>
  <div>
    name: {{ name }}
    birth: {{ birth }}
    age: {{ age }}
  </div>
</template>
<script lang="ts">
import { defineComponent, computed } from 'vue'

export default defineComponent({
  name: 'TestCompositionItem',
  props: {
    name: {
      type: String,
      required: true
    },
    birth: {
      type: Number,
      required: true
    }
  },
  setup (props) {
    const age = computed(() => { return 2021 - props.birth })
    return { age }
  }
})
</script>
