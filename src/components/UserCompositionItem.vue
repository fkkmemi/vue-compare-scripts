<template>
  <q-item>
    <q-item-section avatar>
      {{item.no}}
    </q-item-section>
    <q-item-section>
      <q-item-label>{{item.name}}</q-item-label>
      <q-item-label caption>{{age}}</q-item-label>
    </q-item-section>
    <q-item-section>
      <q-input v-model="name"></q-input>
    </q-item-section>
    <q-item-section side>
      <q-btn color="primary" icon="check" label="OK" @click="updateName" />
    </q-item-section>
  </q-item>
</template>
<script lang="ts">
import { defineComponent, PropType, ref, computed } from 'vue'
import UserInfo from 'src/types/UserInfo'

export default defineComponent({
  name: 'UserItemComposition',
  props: {
    item: {
      type: Object as PropType<UserInfo>,
      required: true
    }
  },
  emits: ['updateName'],
  setup (props, { emit }) {
    const name = ref(props.item.name)
    const age = computed(() => `${2021 - props.item.birth} 살`)
    const updateName = () => emit('updateName', props.item.no, name.value)

    return {
      name,
      age,
      updateName
    }
  }
})
</script>
