<script setup lang="ts">
import Introduction from "../Introduction.vue";
import projects from "../../content/hero/projects.json";

const handleClick = () => {
  alert("Create account button was clicked");
};
</script>

<template>
  <section id="hero" class="section text-center">
    <h2 class="visually-hidden">Hero</h2>
    <div class="container">
      <div id="carouselHero" class="carousel slide">
        <div class="carousel-indicators custom-indicators d-flex">
          <button
            v-for="(project, index) in projects"
            type="button"
            data-bs-target="#carouselHero"
            :key="index"
            :data-bs-slide-to="index"
            :class="['pagination-btn', index === 0 ? 'active' : '']"
            :aria-current="index === 0 ? 'true' : false"
            :aria-label="'Slide ' + index"
          ></button>
        </div>
        <ul class="carousel-inner">
          <li
            v-for="(project, index) in projects"
            :key="index"
            :class="['carousel-item', index === 0 ? 'active' : '']"
          >
            <Introduction
              :name="project.name"
              :motto="project.motto"
              :text="project.text"
            />
          </li>
        </ul>
        <button
          class="carousel-control carousel-control-prev"
          type="button"
          data-bs-target="#carouselHero"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control carousel-control-next"
          type="button"
          data-bs-target="#carouselHero"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
      <button class="hero-button btn" @click="handleClick">
        Create an Account
      </button>
    </div>
  </section>
</template>

<style scoped lang="scss">
#hero {
  background: linear-gradient(rgba($color-background, 0.5)),
    url("../../assets/images/hero/hero-background.webp");

  @include background-center;

  @media screen and (min-width: $bp-tablet-width) {
    padding-top: 25.3rem;
    padding-bottom: 16.3rem;
  }

  @media (-webkit-min-device-pixel-ratio: 2),
    (min-resolution: 192dpi),
    (min-resolution: 2dppx) {
    background: linear-gradient(rgba($color-background, 0.5)),
      url("../../assets/images/hero/hero-background@2x.webp");
  }
}

.carousel {
  margin-bottom: 3rem;
  padding-bottom: 3rem;

  display: flex;
  justify-content: center;

  @media screen and (min-width: $bp-tablet-width) {
    margin-bottom: 5.8rem;
    padding-bottom: 5.8rem;
  }
}

.carousel-inner {
  width: 70%;

  @media screen and (min-width: $bp-tablet-width) {
    width: 48rem;
  }

  @media screen and (min-width: $bp-laptop-width) {
    width: 73.6rem;
  }
}

.carousel-control {
  height: 17rem;

  &.carousel-control-prev {
    justify-content: start;
  }

  &.carousel-control-next {
    justify-content: end;
  }

  & .carousel-control-prev-icon,
  & .carousel-control-next-icon {
    width: 1.1rem;
    height: 3.5rem;
  }
}

.hero-button {
  width: 16rem;
  height: 6rem;

  @include font-18;
  font-size: 1.6rem;
  text-align: center;
  vertical-align: middle;
  border-radius: 10rem;

  color: inherit;
  background-color: $color-hero-btn;

  transition: opacity 0.3s ease;

  @media screen and (min-width: $bp-tablet-width) {
    width: 23rem;
    font-size: 1.8rem;
  }

  &:hover {
    opacity: 0.7;
  }
}
</style>
