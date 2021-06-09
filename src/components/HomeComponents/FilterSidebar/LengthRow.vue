<template>
  <div class="flex flex-wrap px-4">
    <div class="w-full mb-8">
      <h1 class="font-bold">Length</h1>
    </div>
    <div class="w-full">
      <double-range-slider
        sliderId="length-slider"
        :min="lengthMin"
        :max="lengthMax"
        @update:min="value => lengthMin = value"
        @update:max="value => lengthMax = value"
      />
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import DoubleRangeSlider from '@/components/Global/DoubleRangeSlider.vue'

export default defineComponent({
  name: 'LengthRow',
  components: {
    DoubleRangeSlider,
  },
  data() {
    return {
      lengthMin: -100,
      lengthMax: 100,
    }
  },
})
</script>

<style>
</style>