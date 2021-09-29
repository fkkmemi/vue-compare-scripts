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
import { defineComponent, PropType } from 'vue'
import UserInfo from 'src/types/UserInfo'

export default defineComponent({
  name: 'UserItemOption',
  props: {
    item: {
      type: Object as PropType<UserInfo>,
      required: true
    }
  },
  emits: ['updateName'],
  data () {
    return {
      name: this.item.name
    }
  },
  computed: {
    age () {
      return `${2021 - this.item.birth} 살`
    }
  },
  methods: {
    updateName () {
      this.$emit('updateName', this.item.no, this.name)
    }
  }
})
</script>
