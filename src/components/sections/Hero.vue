<script setup>
import Button from "../Button.vue";
import Introduction from "../Introduction.vue";
import projects from "../../content/hero/projects.json";
</script>

<template>
  <section id="hero" class="px-4 py-5 text-center">
    <div class="container py-5">
      <h2 class="visually-hidden">Hero</h2>
      <div
        id="carouselExampleIndicators"
        class="carousel slide"
        data-ride="carousel"
      >
        <ol class="carousel-indicators">
          <li
            v-for="(project, index) in projects"
            :key="index"
            data-target="#carouselExampleIndicators"
            :data-slide-to="index"
            :class="index === 0 ? 'active' : ''"
          ></li>
        </ol>
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
        <a
          class="carousel-control-prev"
          href="#carouselExampleIndicators"
          role="button"
          data-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="sr-only">Previous</span>
        </a>
        <a
          class="carousel-control-next"
          href="#carouselExampleIndicators"
          role="button"
          data-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="sr-only">Next</span>
        </a>
      </div>

      <div class="d-grid gap-2 d-sm-flex justify-content-sm-center">
        <Button
          customClass="btn btn-primary btn-lg px-4 gap-3"
          label="Create an account"
          @click="handleClick"
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  components: { Button },
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
