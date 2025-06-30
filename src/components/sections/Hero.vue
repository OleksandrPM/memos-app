<script setup>
import Introduction from "../Introduction.vue";
import projects from "@/content/hero/projects.json";
</script>

<template>
  <section id="hero" class="px-4 py-5 text-center">
    <div class="container py-5">
      <h2 class="visually-hidden">Hero</h2>
      <div id="carouselExampleIndicators" class="carousel slide">
        <div class="carousel-indicators">
          <button
            type="button"
            data-bs-target="#carouselExampleIndicators"
            v-for="(project, index) in projects"
            :key="index"
            :data-bs-slide-to="index"
            :class="index === 0 ? 'active' : ''"
            :aria-current="index === 0 ? 'true' : ''"
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
          class="carousel-control-prev"
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next"
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>

      <div class="d-grid gap-2 d-sm-flex justify-content-sm-center">
        <button
          class="btn btn-primary rounded-pill btn-lg px-4"
          @click="handleClick"
        >
          Create an account
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    handleClick() {
      console.log("Create account button was clicked");
    },
  },
};
</script>

<style scoped>
#hero {
  background: linear-gradient(rgba(47, 24, 147, 0.5)),
    url("../../assets/images/hero/hero-background.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

@media (-webkit-min-device-pixel-ratio: 2),
  (min-resolution: 192dpi),
  (min-resolution: 2dppx) {
  #hero {
    background: linear-gradient(rgba(47, 24, 147, 0.5)),
      url("../../assets/images/hero/hero-background.jpg");
  }
}
</style>
