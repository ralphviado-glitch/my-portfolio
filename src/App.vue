<script setup>
import Navbar from './components/Navbar.vue';
import Contact from './components/Contact.vue';
import FooterComponent from './components/FooterComponent.vue';
</script>

<template>
  <Navbar />
  <router-view />
  <Contact />
  <FooterComponent />
</template>

<style scoped>

</style>
