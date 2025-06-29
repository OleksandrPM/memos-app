<script setup lang="ts">
import Header from "./components/sections/Header.vue";
import Hero from "./components/sections/Hero.vue";
import Features from "./components/sections/Features.vue";
import CallToAction from "./components/sections/CallToAction.vue";
import Contact from "./components/sections/Contact.vue";
import Pricing from "./components/sections/Pricing.vue";
import Footer from "./components/sections/Footer.vue";
</script>

<template>
  <Header />
  <main>
    <Hero />
    <Features />
    <CallToAction />
    <Contact />
    <Pricing />
  </main>
  <Footer />
</template>

<style scoped></style>
