<template>
  <button @click="handleClick">{{ label }}</button>
</template>

<script>
export default {
  name: "Button",
  props: { label: { type: String, default: "Click me" } },
  methods: {
    handleClick() {
      this.$emit("click");
    },
  },
};
</script>
