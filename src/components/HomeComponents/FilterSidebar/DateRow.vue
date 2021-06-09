<template>
  <div class="flex flex-wrap px-4">
    <div class="w-full">
      <h1 class="font-bold">Date</h1>
    </div>
    <div class="flex flex-wrap w-full mt-1">
      <div class="w-1/2 pr-4">
        <h1 class="text-sm">from</h1>
        <input
          type="text"
          class="w-full border-pc-dark-gray rounded-5 text-center mt-2"
          v-model="fromDate"
        />
      </div>
      <div class="w-1/2 pl-4">
        <h1 class="text-sm">to</h1>
        <input
          type="text"
          class="w-full border-pc-dark-gray rounded-5 text-center mt-2"
          v-model="toDate"
        />
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'DateRow',

  setup() {
    let fromDate = ref('8/8/2021')
    let toDate = ref('8/15/2021')

    return {
      fromDate,
      toDate,
    }
  },
})
</script>

<style>
</style>