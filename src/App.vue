<template>
  <Header />
  <div class="container my-3">
    <router-view />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Header from './components/Header.vue'
export default defineComponent({
  components: { Header }
})
</script>
