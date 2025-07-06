<script setup lang="ts">
import allAdvantages from "../content/pricing/allAdvantages.json";

defineProps<{
  name: string;
  price: string;
  advantages: string[];
}>();

const handleClick = (e: Event): void => {
  const target = e.currentTarget as HTMLElement;
  alert(`You've chosen plan ${target.dataset.plan}`);
};
</script>

<template>
  <div class="pricing-card text-start">
    <h4>{{ name }}</h4>
    <h3>{{ price }}<span>$</span></h3>
    <ul class="d-flex flex-column">
      <li
        v-for="(advantage, index) in allAdvantages"
        :key="index"
        :class="{ marked: advantages.includes(advantage) }"
      >
        {{ advantage }}
      </li>
    </ul>
    <button class="btn" type="button" @click="handleClick" :data-plan="name">
      Get Started
    </button>
  </div>
</template>

<style scoped lang="scss">
.pricing-card {
  width: 100%;
  padding: 4rem 4rem 4rem 4rem;

  border: 0.2rem solid rgba($color-pricing-border, 0.2);
  border-radius: 1rem;

  @media screen and (min-width: $bp-tablet-width) {
    max-width: 37rem;
    padding: 6.42rem 6.9rem 5.6rem 6.9rem;
  }
}

h4 {
  margin-bottom: 1rem;

  @include font-base;
  font-family: $font-normal;

  @media screen and (min-width: $bp-tablet-width) {
    margin-bottom: 2.26rem;
  }
}

h3 {
  margin-bottom: 1.5rem;

  display: flex;
  align-items: start;

  @include font-58;

  @media screen and (min-width: $bp-tablet-width) {
    margin-bottom: 4.46rem;
  }

  & span {
    padding-left: 1rem;

    @include font-16;
  }
}

ul {
  margin-bottom: 3rem;
  gap: 1rem;
}

li {
  position: relative;
  display: flex;
  align-items: center;

  @include font-16;

  opacity: 0.7;

  &::before {
    content: "";
    position: absolute;
    left: -2.5rem;
    display: inline-block;
    width: 1.2rem;
    height: 0.8rem;
    margin-right: 1.3rem;
  }

  & .marked {
    opacity: 1;

    &::before {
      background-image: url("@/assets/images/pricing/check-icon.png");
      @include background-center;
    }
  }
}

.btn {
  width: 23rem;
  height: 6rem;

  border: 0.2rem solid rgba($color-pricing-border, 0.3);
  border-radius: 10rem;
  color: inherit;

  transition: background-color 0.3s ease, border 0.3s ease;

  &:hover {
    border: none;
    background-color: $color-pricing-btn;
  }
}
</style>
