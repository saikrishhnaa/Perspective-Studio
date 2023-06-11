<template>
  <v-card color="basil">
    <TheHeader @toggle-tabpage="toogleTabPage"></TheHeader>
    <v-window>
      <v-window-item :value="currentTab == 'Home'">
        <TheHomePage></TheHomePage>
      </v-window-item>
      <v-window-item :value="currentTab == 'Our Guru'">
        <TheOurGuruPage></TheOurGuruPage>
      </v-window-item>
      <v-window-item :value="currentTab == 'Projects'">
        <TheProjectsPage></TheProjectsPage>
      </v-window-item>
      <v-window-item :value="currentTab == 'Gallery'">
        <TheGalleryPage></TheGalleryPage>
      </v-window-item>
    </v-window>
  </v-card>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

import TheHeader from './components/TheHeader.vue'
import TheHomePage from './views/TheHomePage.vue'
import TheOurGuruPage from './views/TheOurGuruPage.vue'
import TheProjectsPage from './views/TheProjectsPage.vue'
import TheGalleryPage from './views/TheGalleryPage.vue'

const currentTab = ref<string>('Home')

const toogleTabPage = (pageName: string) => {
  currentTab.value = pageName
}
</script>
<style>
body,
html {
  height: 100%;
}
</style>
