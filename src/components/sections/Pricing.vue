<script setup lang="ts">
import PricingCard from "../PricingCard.vue";
import plans from "@/content/pricing/plans.json";
</script>

<template>
  <section id="pricing">
    <div class="container">
      <div class="container py-3">
        <div class="pricing-header p-3 pb-md-4 mx-auto text-center">
          <h2 class="display-4 fw-normal">Plans & Pricing</h2>
          <p class="fs-5">
            Startup Framework is free forever — you only pay for custom domain
            hosting or to export your site.
          </p>
        </div>
        <ul class="list-unstyled row row-cols-1 row-cols-md-3 text-center">
          <li class="col" v-for="(plan, index) in plans" :key="index">
            <PricingCard
              :name="plan.name"
              :price="plan.price"
              :advantages="plan.advantages"
            />
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped>
#pricing {
  background-color: rgba(47, 24, 147, 1);
}
</style>
