<template>
  <h4>{{ name }}</h4>
  <h1 class="display-5 fw-bold">{{ motto }}</h1>
  <div class="col-lg-6 mx-auto">
    <p class="lead mb-4">
      {{ text }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Introduction",
  props: {
    name: { type: String, default: "Introduction`s name" },
    motto: { type: String, default: "Motto" },
    text: { type: String, default: "Introduction`s text" },
  },
};
</script>
