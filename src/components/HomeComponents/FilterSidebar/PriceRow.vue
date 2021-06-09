<template>
  <div class="flex flex-wrap px-4">
    <div class="w-full mb-8">
      <h1 class="font-bold">Price</h1>
    </div>
    <div class="w-full">
      <double-range-slider
        sliderId="price-slider"
        :min="priceMin"
        :max="priceMax"
        @update:min="value => priceMin = value"
        @update:max="value => priceMax = value"
      />
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import DoubleRangeSlider from '@/components/Global/DoubleRangeSlider.vue'

export default defineComponent({
  name: 'PriceRow',
  components: {
    DoubleRangeSlider,
  },
  data() {
    return {
      priceMin: -100,
      priceMax: 100,
    }
  },
})
</script>

<style>
</style>