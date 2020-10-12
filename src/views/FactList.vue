<script lang="ts">
import { defineComponent } from 'vue'
import { facts } from '@/assets/facts'
import { useRouter } from 'vue-router'

export default defineComponent({
  setup() {
    const router = useRouter()
    const goToFact = (id: number) => {
      router.push({ path: `/fact/${id}` })
    }
    return { facts, goToFact }
  }
})
</script>

<template>
  <div class="list-group">
    <a
      class="list-group-item list-group-item-action clickable"
      v-for="(fact, i) in facts"
      :key="i"
      @click="goToFact(i)"
    >
      <div class="row">
        <div class="col-2"><img :src="fact.image" height="40" /></div>
        <div class="col-10 align-self-center">{{ fact.text }}</div>
      </div>
    </a>
  </div>
</template>

<style scoped>
.clickable {
  cursor: pointer;
}
</style>
