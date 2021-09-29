<template>
  <div class="row justify-around q-pa-sm">
    <q-card class="col-5">
      <q-card-section>
        options
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
import { defineComponent } from 'vue'
import UserInfo from 'src/types/UserInfo'
import UserItem from 'src/components/UserOptionItem.vue'

export default defineComponent({
  name: 'IndexOption',
  components: { UserItem },
  data () {
    return {
      name: '',
      birth: 2000,
      items: <UserInfo[]>[]
    }
  },
  methods: {
    submit () {
      const user = {
        no: this.items.length,
        name: this.name,
        birth: this.birth
      }
      this.items.push(user)
      this.name = ''
      this.birth = 2000
    },
    onUpdateName (no: number, name: string) {
      const item = this.items[no]
      item.name = name
    }
  }
})
</script>
