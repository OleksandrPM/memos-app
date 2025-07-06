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
      'head section',
      'sticky-top position-fixed w-100 transition',
      { 'bg-dark bg-opacity-25 shadow-sm backdrop-blur': isScrolled },
    ]"
  >
    <div class="container">
      <Navigation />
    </div>
  </header>
</template>

<style scoped lang="scss">
.head {
  padding-top: 5vw;
  padding-bottom: 2vw;

  @media screen and (min-width: $bp-tablet-width) {
    padding-top: 3rem;
    padding-bottom: 3rem;
  }

  @media screen and (min-width: $bp-laptop-width) {
    padding-top: 8.5rem;
    padding-bottom: 5rem;
  }
}

.container {
  padding-right: 5vw;

  @media screen and (min-width: $bp-tablet-width) {
    padding-right: 0;
  }
}

.transition {
  transition: background-color 0.3s ease, box-shadow 0.3s ease,
    backdrop-filter 0.3s ease;
}
.backdrop-blur {
  backdrop-filter: blur(10px);
}
</style>
