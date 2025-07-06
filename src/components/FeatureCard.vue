<script setup lang="ts">
const props = defineProps<{
  name: string;
  description: string;
  badgePath: string;
  badgeWidth: string;
  badgeHeight: string;
}>();
</script>

<template>
  <div class="feature-card d-flex flex-column">
    <div class="feature-icon-small d-inline-flex align-items-center">
      <svg
        class="bi"
        :width="props.badgeWidth"
        :height="props.badgeHeight"
        aria-hidden="true"
      >
        <use :href="props.badgePath"></use>
      </svg>
    </div>
    <h4 class="feature-title">{{ props.name }}</h4>
    <p class="feature-text">
      {{ props.description }}
    </p>
  </div>
</template>

<style scoped lang="scss">
.feature-icon-small {
  margin-bottom: 2.9rem;
}

.feature-title {
  margin-bottom: 1.62rem;

  @include font-14;
  font-size: 1rem;

  @media screen and (min-width: $bp-tablet-width) {
    font-size: 1.4rem;
  }
}

.feature-text {
  @include font-16;
  font-size: 1.2rem;

  @media screen and (min-width: $bp-tablet-width) {
    font-size: 1.6rem;
  }
}
</style>
