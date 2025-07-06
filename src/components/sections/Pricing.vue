<script setup lang="ts">
import PricingCard from "../PricingCard.vue";
import plans from "../../content/pricing/plans.json";
</script>

<template>
  <section id="pricing" class="section">
    <div class="container text-center">
      <h2 class="title">Plans & Pricing</h2>
      <p class="text mx-auto">
        Startup Framework is free forever — you only pay for custom domain
        hosting or to export your site.
      </p>
      <ul
        class="list-unstyled row row-cols-1 row-cols-md-2 row-cols-xxl-3 text-center d-flex row-gap-5"
      >
        <li class="col" v-for="(plan, index) in plans" :key="index">
          <PricingCard
            :name="plan.name"
            :price="plan.price"
            :advantages="plan.advantages"
          />
        </li>
      </ul>
    </div>
  </section>
</template>

<style lang="scss">
.title {
  margin-bottom: 3rem;

  @include font-42;
}

.text {
  margin-bottom: 5.4rem;
  max-width: 58.6rem;

  @include font-base;
}
</style>
