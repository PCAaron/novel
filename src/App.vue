<template>
  <router-view />
</template>

<script lang="ts">
import { ref, provide } from 'vue'
export default {
  name: 'App',
  setup() {
    const _width = document.documentElement.clientWidth
    const asideVisible = ref( _width <= 768 ? false : true)
    provide('asideShow', asideVisible)
  }
}
</script>
