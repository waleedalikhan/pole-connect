<template>
  <div
    class="w-full bg-white py-2 border-l-13 rounded-5"
    :class="[classType === 'in-person' ? 'border-pc-teal' : '', classType === 'virtual' ? 'border-pc-navy-blue' : '']"
  >
    <div class="flex flex-wrap items-center pl-3 pr-6">
      <div class="w-1/2 flex items-start">
        <div class="h-43px w-43px bg-pc-dark-gray mr-3 mt-1"></div>
        <div>
          <p class="text-pc-navy-blue mb-1">{{ classTitle }}</p>
          <p class="text-pc-navy-blue mb-1 text-sm">{{ classInstructor }}</p>
          <p class="text-pc-navy-blue mb-1">{{ studioName }}</p>
          <p class="text-pc-navy-blue mb-1 text-sm">{{ location }}</p>
        </div>
      </div>
      <div class="w-1/2 flex flex-wrap justify-end">
        <div class="w-full text-right mb-2 pr-5">
          <p class="text-xl">{{ classPrice }}</p>
        </div>
        <button
          class="bg-pc-banner-blue outline-none focus:outline-none px-6 py-2 rounded-50px text-white"
        >Sign Up</button>
      </div>
    </div>
    <div class="w-full border-t border-pc-light-gray pt-3 pb-1 px-4">
      <p class="text-pc-navy-blue">{{ datePublished }}</p>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ProductCard',
  props: {
    classType: {
      type: String,
      default: 'virtual',
    },
    classTitle: String,
    classInstructor: String,
    studioName: String,
    location: String,
    datePublished: String,
    classPrice: String,
  },
})
</script>

<style>
</style>