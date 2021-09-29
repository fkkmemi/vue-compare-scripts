<script setup lang="ts">
import { defineProps, computed } from 'vue'
const props = defineProps<{ name: string, birth: number }>()
const age = computed(() => { return 2021 - props.birth })
</script>
<template>
  <h5>
    TestSetupItem
  </h5>
  <div>
    name: {{ name }}
    birth: {{ birth }}
    age: {{ age }}
  </div>
</template>
