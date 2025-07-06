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
  <section id="features" class="section d-flex">
    <h2 class="visually-hidden">Features</h2>
    <div class="img-thumb">
      <img
        class="mockup"
        srcset="
          ../../assets/images/features/Mockup.png    1x,
          ../../assets/images/features/Mockup@2x.png 2x
        "
        src="../../assets/images/features/Mockup.png"
        min-width="264"
        alt="Laptop"
        loading="lazy"
      />
    </div>
    <div class="container features-container">
      <div
        id="carouselFeatures"
        class="carousel vertical slide flex-column align-items-start"
        data-bs-interval="false"
      >
        <h3 class="carousel-title">We Create Something New</h3>
        <p class="carousel-text">
          We have created a new product that will help designers, developers and
          companies create websites for their startups quickly and easily.
        </p>
        <div
          class="carousel-indicators custom-indicators features-carousel-indicators d-flex flex-column"
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
            <div class="item-group item">
              <FeatureCard
                v-for="(item, i) in group"
                :key="i"
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
  </section>
</template>

<style scoped lang="scss">
#features {
  position: relative;
  display: flex;
  align-items: center;
  gap: 3.345rem;

  background: linear-gradient(rgba($color-background, 0.4)),
    url("../../assets/images/features/features-background.webp");

  background-position: center, center;
  background-size: cover, cover;
  background-repeat: no-repeat, no-repeat;

  @media screen and (min-width: $bp-tablet-width) {
    padding-top: 10rem;
    padding-bottom: 10rem;
    padding-right: 11.5rem;
    padding-left: 0;
  }

  @media (-webkit-min-device-pixel-ratio: 2),
    (min-resolution: 192dpi),
    (min-resolution: 2dppx) {
    background: linear-gradient(rgba($color-background, 0.4)),
      url("../../assets/images/features/features-background@2x.webp");
  }
}

.img-thumb {
  display: none;

  @media screen and (min-width: $bp-tablet-width) {
    display: block;
    width: 34.4vw;
    min-width: 34.4vw;
  }
}

.mockup {
  width: 100%;
  height: auto;
}

.features-container {
  @media screen and (min-width: $bp-tablet-width) {
    width: max-content;
  }
}

.carousel {
  padding-right: 5vw;
  @media screen and (min-width: $bp-tablet-width) {
    padding-right: 16.9rem;
  }
}

.carousel-title {
  margin-bottom: 2rem;

  @include font-42;

  @media screen and (max-width: calc($bp-tablet-width - 0.02px)) {
    margin-bottom: 1.2rem;
    font-size: 3rem;
  }
}

.carousel-text {
  margin-bottom: 6.56rem;

  @include font-base;

  @media screen and (max-width: calc($bp-tablet-width - 0.02px)) {
    margin-bottom: 3rem;
  }
}

.carousel-indicators {
  position: absolute;
  top: 0;
  right: 0;
  margin: 0;
  align-items: end;
  z-index: unset;

  @media screen and (max-width: calc($bp-tablet-width - 0.02px)) {
    gap: 3rem;
  }
}

.item-group {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;

  @media screen and (min-width: $bp-tablet-width) {
    gap: 2.9rem;
  }
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
