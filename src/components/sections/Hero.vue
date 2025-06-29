<script setup>
import Button from "../Button.vue";
import Introduction from "../hero/Introduction.vue";
import projects from "../../content/projects.json";
</script>

<template>
  <section>
    <h2>Hero section</h2>
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

    <Button label="Create an account" @click="handleClick" />
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
