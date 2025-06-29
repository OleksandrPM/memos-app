<template>
  <div class="col d-flex flex-column gap-2">
    <div class="feature-icon-small d-inline-flex align-items-center">
      <svg
        class="bi"
        :width="badgeWidth"
        :height="badgeHeight"
        aria-hidden="true"
      >
        <use :href="badgePath"></use>
      </svg>
    </div>
    <h4 class="fw-semibold mb-0">{{ name }}</h4>
    <p class="">
      {{ description }}
    </p>
  </div>
</template>

<script>
export default {
  name: "FeatureCard",
  props: {
    name: { type: String, default: "Feature`s name" },
    description: { type: String, default: "" },
    badgePath: { default: "/memos-app/src/assets/diamond.svg" },
    badgeWidth: { type: String, default: "44" },
    badgeHeight: { type: String, default: "35" },
  },
};
</script>
