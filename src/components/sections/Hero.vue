<script setup>
import Button from "../Button.vue";
</script>

<template>
  <section>
    <h1>Hero section</h1>
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
