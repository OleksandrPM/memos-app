<script setup lang="ts">
import allAdvantages from "../content/pricing/allAdvantages.json";

defineProps<{
  name: string;
  price: string;
  advantages: string[];
}>();

const handleClick = (e: Event): void => {
  const target = e.currentTarget as HTMLElement;
  alert(`You've chosen plan ${target.dataset.plan}`);
};
</script>

<template>
  <div class="pricing-card p-5 border rounded-4">
    <h5 class="mb-2">{{ name }}</h5>
    <h2 class="mb-4">{{ price }}<span>$</span></h2>
    <ul class="list-unstyled d-flex flex-column gap-2 mb-3">
      <li
        v-for="(advantage, index) in allAdvantages"
        :key="index"
        :class="{ marked: advantages.includes(advantage) }"
      >
        {{ advantage }}
      </li>
    </ul>
    <button
      class="btn btn-outline-primary btn-lg rounded-pill border text-inherit"
      type="button"
      @click="handleClick"
      :data-plan="name"
    >
      Get Started
    </button>
  </div>
</template>

<style scoped>
.marked {
  color: red;
}
</style>
