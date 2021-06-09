<template>
  <div>
    <AccordionComponent accordionTitle="Studio Amenities">
      <div v-for="(amenity, index) in amenitiesData" :key="index" class="w-full mb-6">
        <checkbox
          :isChecked="amenity.isChecked"
          :checkedValue="amenity.checkedValue"
          :onCheck="() => toggleCheckedValue(index)"
          isLarge
        />
      </div>
    </AccordionComponent>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import AccordionComponent from '@/components/Global/AccordionComponent.vue'
import Checkbox from '@/components/Global/Checkbox.vue'

export default defineComponent({
  name: 'Amenities',
  components: {
    AccordionComponent,
    Checkbox,
  },
  setup() {
    let amenitiesData = ref([
      {
        id: 1,
        isChecked: false,
        checkedValue: 'food/drinks',
      },
      {
        id: 2,
        isChecked: false,
        checkedValue: 'lockers',
      },
      {
        id: 3,
        isChecked: false,
        checkedValue: 'parking',
      },
      {
        id: 4,
        isChecked: false,
        checkedValue: 'rentals',
      },
      {
        id: 5,
        isChecked: false,
        checkedValue: 'showers',
      },
    ])

    const toggleCheckedValue = index => {
      amenitiesData.value[index].isChecked = !amenitiesData.value[index].isChecked
    }

    return {
      amenitiesData,
      toggleCheckedValue,
    }
  },
})
</script>

<style>
</style>