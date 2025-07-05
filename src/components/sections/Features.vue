<script setup lang="ts">
import { computed } from "vue";

import FeatureCard from "../FeatureCard.vue";
import features from "../../content/features/features.json";

const groupedFeatures = computed(() => {
  const result = [];

  for (let i = 0; i < features.length; i += 2) {
    result.push(features.slice(i, i + 2));
  }

  return result;
});
</script>

<template>
  <section id="features">
    <h2 class="visually-hidden">Features</h2>
    <div class="row">
      <div class="col-4 d-none d-md-block">
        <img
          class="mockup"
          src="../../assets/images/features/Mockup.png"
          alt="laptop"
        />
      </div>
      <div
        id="carouselFeatures"
        class="vertical carousel slide col-md-7 d-flex flex-column align-items-start gap-2 pe-5"
        data-bs-interval="false"
      >
        <h2 class="fw-bold">We Create Something New</h2>
        <p class="">
          We have created a new product that will help designers, developers and
          companies create websites for their startups quickly and easily.
        </p>
        <div
          class="carousel-indicators custom-indicators features-carousel-indicators d-flex flex-column gap-3"
        >
          <button
            v-for="(group, index) in groupedFeatures"
            type="button"
            data-bs-target="#carouselFeatures"
            :key="index"
            :data-bs-slide-to="index"
            :class="index === 0 ? 'active' : ''"
            :aria-current="index === 0 ? 'true' : undefined"
            :aria-label="'Slide ' + index"
          ></button>
        </div>
        <div class="carousel-inner">
          <div
            v-for="(group, index) in groupedFeatures"
            :class="['carousel-item', index === 0 ? 'active' : '']"
            :key="index"
          >
            <div class="item-group item row">
              <div v-for="(item, i) in group" :key="i" class="col">
                <FeatureCard
                  :name="item.name"
                  :description="item.description"
                  :badgePath="item.badgePath"
                  :badgeWidth="item.badgeWidth"
                  :badgeHeight="item.badgeHeight"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
#features {
  position: relative;

  padding-top: 6.25rem;
  padding-bottom: 6.25rem;

  background: linear-gradient(rgba($color-background, 0.4)),
    url("../../assets/images/features/features-background.webp");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;

  @media (-webkit-min-device-pixel-ratio: 2),
    (min-resolution: 192dpi),
    (min-resolution: 2dppx) {
    #features {
      background: linear-gradient(rgba($color-background, 0.4)),
        url("../../assets/images/features/features-background@2x.webp");
    }
  }
}

.mockup {
  width: 100%;
}

.carousel-indicators {
  position: absolute;
  top: 0;
  right: 0;
  margin: 0;
  align-items: end;
}

.carousel-item-prev:not(.carousel-item-end),
.active.carousel-item-start {
  -webkit-transform: translate3d(0, -100%, 0);
  transform: translate3d(0, -100%, 0);
}

.carousel-item-next:not(.carousel-item-start),
.active.carousel-item-end {
  -webkit-transform: translate3d(0, 100%, 0);
  transform: translate3d(0, 100%, 0);
}
</style>
