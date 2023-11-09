<template>
  <div class="h-screen w-screen bg-slate-800 text-slate-50 overflow-hidden first-section">
    <Front />
    <Horizontal 
      v-motion
      :initial="{ opacity: 0, y: 20 }"
      :enter="{ opacity: 1, y: 0, scale: 1 }"
      :delay="300"
    />
  </div>
  <div>
    <Contacts />
    <FooterComponent />
  </div>
</template>

<script setup>
import Front from './modules/FrontModule/FrontModule.vue'
import Horizontal from './modules/FrontModule/HorizontalScrollModule.vue'
import Contacts from './modules/ContactsModule/ContactsModule.vue'
import FooterComponent from './modules/ContactsModule/components/FooterComponent.vue'
// data

// methods


</script>

<style>
#app {
  font-family: 'Playfair Display', serif;
}
</style>
