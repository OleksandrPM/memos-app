<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";
import DribbleIcon from "./DribbleIcon.vue";
import BehanceIcon from "./BehanceIcon.vue";

const activeLink = ref("hero");

const links = [
  { id: "hero", label: "Home" },
  { id: "features", label: "Features" },
  { id: "pricing", label: "Pricing" },
  { id: "blog", label: "Blog" },
  { id: "hero", icon: DribbleIcon },
  { id: "pricing", icon: BehanceIcon },
];

function setActive(id: string) {
  activeLink.value = id;
}

function onScroll() {
  const sectionsEl = document.querySelectorAll("section");
  const scrollY = window.scrollY;

  sectionsEl.forEach((section) => {
    const top = section.offsetTop - 100;
    const bottom = top + section.offsetHeight;
    if (scrollY >= top && scrollY < bottom) {
      activeLink.value = section.id;
    }
  });
}

onMounted(() => {
  window.addEventListener("scroll", onScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", onScroll);
});
</script>

<template>
  <nav
    class="navbar navbar-expand-md w-100 d-flex"
    aria-label="Fourth navbar example"
  >
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarsExample04"
      aria-controls="navbarsExample04"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div
      class="collapse navbar-collapse justify-content-center md-bg-dark bg-opacity-75"
      id="navbarsExample04"
    >
      <ul class="navbar-nav d-flex justify-content-center">
        <li v-for="(link, index) in links" :key="index" class="nav-item">
          <a
            v-if="link.label || link.icon"
            :href="`#${link.id}`"
            :class="[
              'nav-link text-white',
              { current: activeLink === link.id },
            ]"
            @click="setActive(link.id)"
          >
            <span v-if="link.icon" class="me-1">
              <component :is="link.icon" />
            </span>
            {{ link.label }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped lang="scss">
.navbar {
  padding: 0;
}

.navbar-toggler {
  margin-left: auto;

  color: white;
  border-color: white;

  transition: color 0.3s ease, border-color 0.3s ease;

  &:hover {
    color: RGBA(86, 94, 100, var(--bs-link-opacity, 1));
    border-color: RGBA(86, 94, 100, var(--bs-link-opacity, 1));

    & .navbar-toggler-icon {
      background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='RGBA(86, 94, 100, var(--bs-link-opacity, 1))' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");
    }
  }
}

.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='white' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");

  transition: background-image 0.3s ease;
}

.navbar-nav {
  max-height: 80vh;
  padding-top: 10vh;
  padding-bottom: 10vh;
  gap: 1rem;

  overflow-y: auto;

  @media screen and (min-width: $bp-tablet-width) {
    padding-top: 0;
    padding-bottom: 0;
    gap: 2.3rem;

    overflow: hidden;
  }
}

.nav-link {
  padding: 1rem;
  text-align: center;

  cursor: pointer;

  @media screen and (min-width: $bp-tablet-width) {
    @include font-18;
  }

  &:hover {
    border-bottom: 0.2rem solid $color-text-main;
  }

  &.current {
    opacity: 30%;

    @include inactive;
  }
}
</style>
