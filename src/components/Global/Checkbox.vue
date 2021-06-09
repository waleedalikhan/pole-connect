<template>
  <div class="flex items-center" @click="onCheck">
    <div
      class="flex justify-center items-center rounded-5 bg-white border border-pc-dark-gray cursor-pointer"
      :class="[isLarge ? 'h-31px w-31px' : 'w-5 h-5']"
    >
      <div
        v-if="isChecked"
        class="w-10px h-10px rounded-full bg-pc-navy-blue"
        :class="[isLarge ? 'h-14px w-14px' : 'h-10px w-10px']"
      ></div>
    </div>

    <p class="text-pc-night-sky ml-2">{{ checkedValue }}</p>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Checkbox',
  props: {
    isChecked: Boolean,
    onCheck: Function,
    checkedValue: String,
    isLarge: {
      type: Boolean,
      default: false,
    },
  },
})
</script>

<style>
</style>