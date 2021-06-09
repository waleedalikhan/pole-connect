<template>
  <div
    class="fixed z-50 top-0 bottom-0 w-full bg-pc-filter-sidebar min-h-screen px-6 py-6 overflow-y-scroll cool-transition"
    :class="[showSidebar ? 'left-0' : '-left-full']"
  >
    <div class="flex flex-wrap px-4">
      <div class="w-full flex justify-end mb-5">
        <button class="bg-transparent outline-none focus:outline-none" @click="closeSidebar">
          <img src="../../../assets/icons/cross-icon.svg" alt />
        </button>
      </div>
      <div class="w-1/2">
        <p class="text-sm">400 classes found</p>
      </div>
      <div class="w-1/2 flex justify-end">
        <button
          class="bg-transparent outline-none focus:outline-none text-pc-navy-blue font-bold"
        >reset filters</button>
      </div>
    </div>
    <div class="w-full h-px bg-pc-light-gray my-6"></div>
    <class-type-row />
    <div class="w-full h-px bg-pc-light-gray mt-6 mb-4"></div>
    <date-row />
    <div class="w-full h-px bg-pc-light-gray mt-6 mb-4"></div>
    <start-time-row />
    <div class="w-full h-px bg-pc-light-gray mt-6 mb-4"></div>
    <price-row />
    <div class="w-full h-px bg-pc-light-gray mt-6 mb-4"></div>
    <length-row />
    <div class="w-full h-px bg-pc-light-gray mt-6 mb-4"></div>
    <amenities-row />
    <div class="w-full h-px bg-pc-light-gray mt-6 mb-4"></div>
    <tags-row />
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import ClassTypeRow from '@/components/HomeComponents/FilterSidebar/ClassTypeRow.vue'
import DateRow from '@/components/HomeComponents/FilterSidebar/DateRow.vue'
import StartTimeRow from '@/components/HomeComponents/FilterSidebar/StartTimeRow.vue'
import PriceRow from '@/components/HomeComponents/FilterSidebar/PriceRow.vue'
import LengthRow from '@/components/HomeComponents/FilterSidebar/LengthRow.vue'
import AmenitiesRow from '@/components/HomeComponents/FilterSidebar/AmenitiesRow.vue'
import TagsRow from '@/components/HomeComponents/FilterSidebar/TagsRow.vue'

export default defineComponent({
  name: 'FilterSidebar',
  props: {
    showSidebar: {
      type: Boolean,
      default: false,
    },
  },
  components: {
    ClassTypeRow,
    DateRow,
    StartTimeRow,
    PriceRow,
    LengthRow,
    AmenitiesRow,
    TagsRow,
  },
  methods: {
    closeSidebar() {
      this.$emit('close', false)
    },
  },
})
</script>

<style>
</style>