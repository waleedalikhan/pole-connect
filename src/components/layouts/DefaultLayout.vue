<template>
  <div class="w-full">
    <Header />
    <div class="mb-6">
      <slot></slot>
    </div>
    <Footer />
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import Header from '../Global/Header.vue'
import Footer from '../Global/Footer.vue'

export default defineComponent({
  name: 'DefaultLayout',
  components: {
    Header,
    Footer,
  },
})
</script>

<style>
</style>