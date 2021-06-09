<template>
  <div>
    <banner-component />
    <banner-links />
    <div class="bg-pc-sky-blue p-4 w-full">
      <div class="flex items-center">
        <div class="w-1/2">
          <p class="text-pc-navy-blue text-sm">400 classes found</p>
        </div>
        <div class="w-1/2 flex items-center">
          <div class="flex items-center mr-4">
            <div class="w-3 h-3 rounded-full bg-pc-teal mr-2"></div>
            <p class="text-sm text-pc-navy-blue">In-person</p>
          </div>
          <div class="flex items-center">
            <div class="w-3 h-3 rounded-full bg-pc-navy-blue mr-2"></div>
            <p class="text-sm text-pc-navy-blue">In-person</p>
          </div>
        </div>
      </div>
      <div class="flex flex-wrap my-3">
        <div v-for="classObject in classes" :key="classObject.id" class="w-full mb-6">
          <class-card
            :classType="classObject.classType"
            :classTitle="classObject.classTitle"
            :classInstructor="classObject.classInstructor"
            :studioName="classObject.studioName"
            :location="classObject.location"
            :classPrice="classObject.classPrice"
            :datePublished="classObject.datePublished"
          />
        </div>
        <div class="w-full flex justify-center mt-5">
          <button
            class="bg-pc-navy-blue px-8 py-3 text-sm font-semibold text-white rounded-20px"
          >Show More Results</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import BannerComponent from '@/components/HomeComponents/BannerComponent.vue'
import BannerLinks from '@/components/HomeComponents/BannerLinks.vue'
import ClassCard from '@/components/HomeComponents/ClassCard.vue'

export default defineComponent({
  name: 'Home',
  components: {
    BannerComponent,
    BannerLinks,
    ClassCard,
  },
  setup() {
    const classes = [
      {
        id: 1,
        classType: 'virtual',
        classTitle: 'Virtual live flow',
        classInstructor: 'Instructor name',
        studioName: 'Studio Name',
        location: 'Perth, WA, Australia',
        classPrice: '$ 100',
        datePublished: 'Wed, 5/30/2021, 4:15pm - 5:15pm',
      },
      {
        id: 2,
        classType: 'in-person',
        classTitle: 'Spin pole level',
        classInstructor: 'Instructor',
        studioName: 'Live MORE hot yoga',
        location: 'City, State, USA',
        classPrice: '$ 45',
        datePublished: 'Tue, 5/29/2021, 3:15pm - 4:15pm',
      },
      {
        id: 3,
        classType: 'virtual',
        classTitle: 'Virtual live flow',
        classInstructor: 'Instructor name',
        studioName: 'Studio name',
        location: 'Beijing, China',
        classPrice: '$ 15',
        datePublished: 'Wed, 5/30/2021, 4:15pm - 5:15pm',
      },
      {
        id: 4,
        classType: 'in-person',
        classTitle: 'Spin pole level',
        classInstructor: 'Instructor',
        studioName: 'Live MORE hot yoga',
        location: 'Covington, LA, USA',
        classPrice: '$ 45',
        datePublished: 'Tue, 5/29/2021, 3:15pm - 4:15pm',
      },
      {
        id: 5,
        classType: 'virtual',
        classTitle: 'Virtual live flow',
        classInstructor: 'Instructor name',
        studioName: 'Studio Name',
        location: 'City, state, Country',
        classPrice: '$ 50',
        datePublished: 'Wed, 5/30/2021, 4:15pm - 5:15pm',
      },
      {
        id: 6,
        classType: 'virtual',
        classTitle: 'Virtual live flow',
        classInstructor: 'Instructor name',
        studioName: 'Studio Name',
        location: 'City, state, Country',
        classPrice: '$ 30',
        datePublished: 'Wed, 5/30/2021, 4:15pm - 5:15pm',
      },
    ]

    return {
      classes,
    }
  },
})
</script>
