<template>
  <div class="flex flex-wrap px-4">
    <div class="w-full">
      <h1 class="font-bold">Start Time</h1>
    </div>
    <div class="w-full flex justify-between mt-5 mb-14">
      <checkbox
        :isChecked="localTimeCheck"
        :onCheck="toggleLocalTime"
        checkedValue="local time"
        isLarge
      />
      <checkbox
        :isChecked="yourTimeCheck"
        :onCheck="toggleYourTime"
        checkedValue="your time"
        isLarge
      />
    </div>
    <div class="w-full">
      <double-range-slider
        sliderId="time-slider"
        :min="startTimeMin"
        :max="startTimeMax"
        @update:min="value => startTimeMin = value"
        @update:max="value => startTimeMax = value"
      />
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import Checkbox from '@/components/Global/Checkbox.vue'
import DoubleRangeSlider from '@/components/Global/DoubleRangeSlider.vue'

export default defineComponent({
  name: 'StartTimeRow',
  components: {
    Checkbox,
    DoubleRangeSlider,
  },
  setup() {
    let localTimeCheck = ref(false)
    const toggleLocalTime = () => {
      localTimeCheck.value = !localTimeCheck.value
    }

    let yourTimeCheck = ref(true)
    const toggleYourTime = () => {
      yourTimeCheck.value = !yourTimeCheck.value
    }

    let startTimeMin = ref(1)
    let startTimeMax = ref(60)

    return {
      localTimeCheck,
      toggleLocalTime,
      yourTimeCheck,
      toggleYourTime,
      startTimeMin,
      startTimeMax,
    }
  },
})
</script>

<style>
</style>