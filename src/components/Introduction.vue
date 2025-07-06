<script setup lang="ts">
const props = defineProps<{
  name: string;
  motto: string;
  text: string;
}>();
</script>

<template>
  <h4>{{ name }}</h4>
  <h1 class="display-5 fw-bold">{{ motto }}</h1>
  <p>
    {{ text }}
  </p>
</template>

<style scoped lang="scss">
h4 {
  margin-bottom: 2.18rem;

  @include font-24;
}

h1 {
  margin-bottom: 2.72rem;

  font-size: 4rem;
  line-height: 4rem;
  letter-spacing: -0.1rem;

  @media screen and (min-width: $bp-tablet-width) {
    font-size: 7.2rem;
    line-height: 8.6rem;
  }
}

p {
  @include font-base;
}
</style>
