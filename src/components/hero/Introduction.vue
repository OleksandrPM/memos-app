<template>
  <h4>{{ name }}</h4>
  <h1>{{ motto }}</h1>
  <p>
    {{ text }}
  </p>
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
