<template>
  <button :class="customClass" @click="handleClick">{{ label }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    label: { type: String, default: "Click me" },
    customClass: { type: String, default: "" },
  },
  methods: {
    handleClick() {
      this.$emit("click");
    },
  },
};
</script>
