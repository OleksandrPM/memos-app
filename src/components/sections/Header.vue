<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";
import Navigation from "../Navigation.vue";

const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <header
    :class="[
      'sticky-top position-fixed w-100 transition',
      { 'bg-dark bg-opacity-25 shadow-sm backdrop-blur': isScrolled },
    ]"
  >
    <div class="container">
      <div
        class="d-flex flex-wrap align-items-center justify-content-center py-3"
      >
        <Navigation />
      </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
.transition {
  transition: background-color 0.3s ease, box-shadow 0.3s ease,
    backdrop-filter 0.3s ease;
}
.backdrop-blur {
  backdrop-filter: blur(10px);
}
</style>
