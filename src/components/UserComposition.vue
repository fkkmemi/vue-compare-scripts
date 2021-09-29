<template>
  <div class="row justify-around q-pa-sm">
    <q-card class="col-5">
      <q-card-section>
        composition
      </q-card-section>
      <q-card-section>
        <q-input v-model="name" />
        <q-input v-model="birth" type="number" />
      </q-card-section>
      <q-card-actions>
        <q-btn color="primary" icon="check" label="OK" @click="submit" />
      </q-card-actions>
    </q-card>
    <q-card class="col-5">
      <q-card-section>
        users
      </q-card-section>
      <q-list>
        <UserItem
          v-for="item in items"
          :key="item.no"
          :item="item"
          @updateName="onUpdateName"/>
      </q-list>
    </q-card>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import UserInfo from 'src/types/UserInfo'
import UserItem from 'src/components/UserCompositionItem.vue'

export default defineComponent({
  name: 'IndexComposition',
  components: { UserItem },
  setup () {
    const name = ref('')
    const birth = ref(2000)
    const items = ref<UserInfo[]>([])
    function submit () {
      const user = {
        no: items.value.length,
        name: name.value,
        birth: birth.value
      }
      items.value.push(user)
      name.value = ''
      birth.value = 2000
    }
    const onUpdateName = (no: number, name: string) => {
      const item = items.value[no]
      item.name = name
    }
    return {
      name,
      birth,
      items,
      submit,
      onUpdateName
    }
  }
})
</script>
