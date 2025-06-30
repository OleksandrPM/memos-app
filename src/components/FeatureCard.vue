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
  <div class="col d-flex flex-column gap-2">
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
    <h4 class="fw-semibold mb-0">{{ props.name }}</h4>
    <p class="">
      {{ props.description }}
    </p>
  </div>
</template>
