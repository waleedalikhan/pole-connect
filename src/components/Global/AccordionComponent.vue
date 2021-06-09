<template>
  <div class="flex flex-wrap px-4">
    <div
      class="w-full flex items-center justify-between cursor-pointer"
      :class="[view ? 'mb-6' : '']"
      @click="toggleView"
    >
      <h1 class="font-bold">{{ accordionTitle }}</h1>
      <img
        src="@/assets/icons/chevron-icon.svg"
        alt
        class="transform"
        :class="[view ? 'rotate-180' : 'rotate-0']"
      />
    </div>

    <div v-show="view" class="w-full flex flex-wrap">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'AccordionComponent',
  props: {
    accordionTitle: String,
  },
  setup() {
    let view = ref(false)
    const toggleView = () => {
      view.value = !view.value
    }

    return {
      view,
      toggleView,
    }
  },
})
</script>

<style>
</style>