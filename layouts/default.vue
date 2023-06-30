<template>
  <v-app>
    <v-app-bar>
      <v-app-title></v-app-title>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer> </v-footer>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'DefaultLayout',
  setup() {},
})
</script>

<style module></style>
