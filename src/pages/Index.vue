<script setup lang="ts">
import { ref } from 'vue'
import UserOption from 'src/components/UserOption.vue'
import UserComposition from 'src/components/UserComposition.vue'
import UserSetup from 'src/components/UserSetup.vue'
import TestOption from 'src/components/TestOption.vue'
import TestComposition from 'src/components/TestComposition.vue'
import TestSetup from 'src/components/TestSetup.vue'
const toggle = ref(false)

</script>
<template>
  <q-page padding>
    <q-toolbar class="bg-purple text-white">
      <q-toggle v-model="toggle" color="green" />
    </q-toolbar>
    <template v-if="toggle">
      <UserOption />
      <UserComposition />
      <UserSetup />
    </template>
    <template v-else>
      <TestOption />
      <TestComposition />
      <TestSetup />
    </template>
  </q-page>
</template>
