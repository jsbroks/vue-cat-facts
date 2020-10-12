<script>
import { computed, defineComponent } from 'vue'
import { useRoute } from 'vue-router'

export default defineComponent({
  props: {
    to: { type: String, required: true },
    exact: { type: Boolean, default: false }
  },
  setup(props) {
    const route = useRoute()
    const active = computed(() =>
      props.exact ? route.path === props.to : route.path.startsWith(props.to)
    )
    return { active }
  }
})
</script>

<template>
  <div style="width: 150px">
    <router-link
      :to="to"
      class="nav-link"
      :class="active ? 'font-weight-bold' : null"
    >
      <slot />
    </router-link>
  </div>
</template>
