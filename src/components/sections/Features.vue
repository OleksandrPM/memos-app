<script setup lang="ts">
import FeatureCard from "../FeatureCard.vue";
import features from "../../content/features/features.json";
</script>

<template>
  <section id="features">
    <h2 class="visually-hidden">Features</h2>
    <div class="row">
      <div class="col-4 d-none d-md-block">
        <img
          src="../../assets/images/features/Mockup.png"
          alt="laptop"
          class="mockup"
        />
      </div>

      <div class="col-md-7">
        <div class="d-flex flex-column align-items-start gap-2">
          <h2 class="fw-bold">We Create Something New</h2>
          <p class="">
            We have created a new product that will help designers, developers
            and companies create websites for their startups quickly and easily.
          </p>
        </div>
        <div class="col">
          <div class="row row-cols-1 row-cols-sm-2 g-4">
            <FeatureCard
              :name="features[0].name"
              :description="features[0].description"
              :badgePath="features[0].badgePath"
              :badgeWidth="features[0].badgeWidth"
              :badgeHeight="features[0].badgeHeight"
            />
            <FeatureCard
              :name="features[1].name"
              :description="features[1].description"
              :badgePath="features[1].badgePath"
              :badgeWidth="features[1].badgeWidth"
              :badgeHeight="features[1].badgeHeight"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
#features {
  position: relative;

  padding-top: 6.25rem;
  padding-bottom: 6.25rem;

  background: linear-gradient(rgba(47, 24, 147, 0.5)),
    url("../../assets/images/features/features-background.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

@media (-webkit-min-device-pixel-ratio: 2),
  (min-resolution: 192dpi),
  (min-resolution: 2dppx) {
  #features {
    background: linear-gradient(rgba(47, 24, 147, 0.5)),
      url("../../assets/images/features/features-background.jpg");
  }
}

.mockup {
  width: 100%;
}
</style>
