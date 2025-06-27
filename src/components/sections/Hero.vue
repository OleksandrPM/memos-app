<script setup>
import Button from "../Button.vue";
import Introduction from "../hero/Introduction.vue";
import projects from "../../content/projects.json";
</script>

<template>
  <section>
    <h2>Hero section</h2>
    <ul>
      <li v-for="(project, index) in projects" :key="index">
        <Introduction
          :name="project.name"
          :motto="project.motto"
          :text="project.text"
        />
      </li>
    </ul>
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
