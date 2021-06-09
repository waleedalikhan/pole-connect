<template>
  <div class="flex flex-wrap px-4">
    <div class="w-full">
      <h1 class="font-bold">Class Type</h1>
    </div>
    <div class="w-full flex my-5 justify-between">
      <checkbox checkedValue="show all" :isChecked="showAllCheck" :onCheck="toggleShowAllCheck" />
      <checkbox checkedValue="virtual" :isChecked="virtualCheck" :onCheck="toggleVirtualCheck" />
      <checkbox checkedValue="in-person" :isChecked="inPersonCheck" :onCheck="toggleInpersonCheck" />
    </div>
    <div class="w-full flex items-center px-3 justify-between rounded-5 border border-pc-dark-gray h-10 bg-white">
      <input type="text" class="placeholder-pc-dark-gray ring-0 focus:ring-0 outline-none focus:outline-none flex-1 bg-transparent border-0 text-xs" placeholder="city, state or country" />
      <img src="@/assets/icons/search-icon.svg" alt="">
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import Checkbox from '@/components/Global/Checkbox.vue'

export default defineComponent({
  name: 'ClassTypeRow',
  components: {
    Checkbox,
  },
  setup() {
    let showAllCheck = ref(false)
    const toggleShowAllCheck = () => {
      showAllCheck.value = !showAllCheck.value
    }

    let virtualCheck = ref(false)
    const toggleVirtualCheck = () => {
      virtualCheck.value = !virtualCheck.value
    }

    let inPersonCheck = ref(false)
    const toggleInpersonCheck = () => {
      inPersonCheck.value = !inPersonCheck.value
    }

    return {
      showAllCheck,
      toggleShowAllCheck,
      virtualCheck,
      toggleVirtualCheck,
      inPersonCheck,
      toggleInpersonCheck,
    }
  },
})
</script>

<style>
</style>