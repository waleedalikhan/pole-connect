<template>
  <div
    class="w-full bg-white py-2 border-l-13 rounded-5"
    :class="[classType === 'in-person' ? 'border-pc-teal' : '', classType === 'virtual' ? 'border-pc-navy-blue' : '']"
  >
    <div class="flex flex-wrap items-center pl-3 pr-6">
      <div class="w-full flex items-start mb-4">
        <div class="h-43px w-43px bg-pc-darker-gray mr-3 mt-1"></div>
        <div>
          <p class="mb-1 font-bold">{{ classTitle }}</p>
        </div>
      </div>
      <div class="w-full flex flex-wrap justify-end">
        <div class="w-full flex items-center mb-2">
          <div class="flex-1">
            <p class="text-sm mb-1">{{ studioName }}</p>
            <p class="mb-1 text-sm">{{ location }}</p>
          </div>
          <div class="flex items-center">
            <div class="bg-pc-sky-blue flex items-center justify-center p-2">
              <p class="font-bold">${{ classPrice }}</p>
            </div>
            <button class="bg-transparent outline-none focus:outline-none transform -rotate-90 ml-1">
              <img src="@/assets/icons/chevron-icon.svg" alt />
            </button>
          </div>
        </div>
      </div>
    </div>
    <div class="flex w-full border-t border-pc-light-gray pt-3 pb-1 px-4 items-center">
      <div class="flex-1">
        <p class="mb-1 text-sm">{{ classInstructor }}</p>
        <p class="text-sm">{{ datePublished }}</p>
      </div>
      <button
        class="bg-pc-banner-blue outline-none focus:outline-none px-8 py-2 rounded-50px text-white"
      >Book</button>
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