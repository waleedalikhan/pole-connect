<template>
  <div>
    <main>
      <default-layout>
        <router-view />
      </default-layout>
    </main>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import DefaultLayout from './components/layouts/DefaultLayout.vue'

export default defineComponent({
  components: {
    DefaultLayout,
  },
})
</script>
