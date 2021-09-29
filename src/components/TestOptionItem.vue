<template>
  <h5>
    TestOptionItem
  </h5>
  <div>
    name: {{ name }}
    birth: {{ birth }}
    age: {{ age }}
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TestOptionItem',
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
  computed: {
    age () {
      return 2021 - this.birth
    }
  }
})
</script>
