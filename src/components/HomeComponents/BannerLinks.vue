<template>
  <div class="flex items-center h-50px px-6 justify-between border border-pc-light-gray">
    <div class="border-r border-black pr-4" @click="toggleSidebar">
      <button class="bg-transparent outline-none focus:outline-none flex items-center">
        <img src="../../assets/icons/filter-icon.svg" alt />
        <span class="text-sm ml-2">Filter</span>
      </button>
    </div>
    <div class="border-r border-black pr-4">
      <button
        class="bg-transparent outline-none focus:outline-none flex items-center"
        @click="onSortClick"
      >
        <img src="../../assets/icons/sort-icon.svg" alt />
        <span class="text-sm ml-2">Sort</span>
      </button>
    </div>
    <div class="border-r border-black pr-4">
      <button class="bg-transparent outline-none focus:outline-none flex items-center">Time : EST</button>
    </div>
    <div>
      <button class="bg-transparent outline-none focus:outline-none flex items-center">$ USD</button>
    </div>

    <filter-sidebar :showSidebar="showSidebar" @close="value => showSidebar = value" />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import FilterSidebar from '@/components/HomeComponents/FilterSidebar/index.vue'

export default defineComponent({
  name: 'BannerLinks',
  props: {
    onSortClick: Function,
  },
  components: {
    FilterSidebar,
  },
  setup() {
    let showSidebar = ref(false)

    let toggleSidebar = () => {
      showSidebar.value = true
    }

    return {
      showSidebar,
      toggleSidebar,
    }
  },
})
</script>

<style>
</style>