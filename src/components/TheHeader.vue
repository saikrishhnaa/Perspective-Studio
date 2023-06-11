<template>
  <v-toolbar>
    <v-toolbar-title class="font-weight-bold text-h5 text-basil"
      >Perspective Studio</v-toolbar-title
    >
    <v-tabs v-model="tab" align-tabs="title" bg-color="transparent" color="basil" grow>
      <v-tab v-for="item in items" :key="item" :value="item">
        {{ item }}
      </v-tab>
    </v-tabs>
  </v-toolbar>
</template>

<script lang="ts" setup>
import { ref, watch } from 'vue'

const tab = ref<string>('Home')

const items = ref<string[]>(['Home', 'Our Guru', 'Projects', 'Gallery'])

const text = ref<string>(
  'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
)

const emits = defineEmits(['toggle-tabpage'])

watch(tab, (val) => {
  emits('toggle-tabpage', val)
})
</script>

<style>
/* Helper classes */
.bg-basil {
  background-color: #fffbe6 !important;
}
.text-basil {
  color: #356859 !important;
}
</style>
