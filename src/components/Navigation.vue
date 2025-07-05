<script setup lang="ts">
// import { ref, onMounted, onUnmounted } from "vue";

// const activeLink = ref("hero");

// const links = [
//   { id: "hero", label: "Home" },
//   { id: "features", label: "Features" },
//   { id: "pricing", label: "Pricing" },
//   { id: "blog", label: "Blog" },
//   { id: "#", label: "ball" },
//   { id: "#", label: "Be" },
// ];

// function setActive(id: string) {
//   activeLink.value = id;
// }

// function onScroll() {
//   const sections = document.querySelectorAll('section')
//   const scrollY = window.scrollY

//   sections.forEach((section) => {
//     const top = section.offsetTop - 100
//     const bottom = top + section.offsetHeight
//     if (scrollY >= top && scrollY < bottom) {
//       activeLink.value = section.id
//     }
//   })
// }

// onMounted(() => {
//   window.addEventListener('scroll', onScroll)
// })

// onUnmounted(() => {
//   window.removeEventListener('scroll', onScroll)
// })
</script>

<template>
  <nav class="navbar navbar-expand-md w-100" aria-label="Fourth navbar example">
    <div class="container-fluid">
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
        class="collapse navbar-collapse md-bg-dark bg-opacity-75"
        id="navbarsExample04"
      >
        <ul class="navbar-nav me-auto mb-2 mb-md-0">
          <li class="nav-item">
            <!-- <a
              v-for="(link, index) in links"
              :key="index"
              :href="`#${link.id}`"
              :class="{ active: activeLink === link.id }"
              @click="setActive(link.id)"
            >
              {{ link.label }}
            </a> -->

            <a
              href="#hero"
              class="nav-link active text-white px-2 link-secondary"
              aria-current="page"
              >Home</a
            >
          </li>
          <li class="nav-item">
            <a href="#features" class="nav-link text-white px-2">Features</a>
          </li>
          <li class="nav-item">
            <a href="#pricing" class="nav-link text-white px-2">Pricing</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link text-white px-2">Blog</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link text-white px-2">
              <svg class="nav-img" width="16" height="21">
                <use href="/sprite.svg#fa-dribbble"></use>
              </svg>
            </a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link text-white px-2">
              <svg class="svg" width="21" height="21">
                <use href="/sprite.svg#fa-behance"></use>
              </svg>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar-toggler {
  color: white;
  border-color: white;

  transition: color 0.3s ease, border-color 0.3s ease;
}

.navbar-toggler:hover {
  color: RGBA(86, 94, 100, var(--bs-link-opacity, 1));
  border-color: RGBA(86, 94, 100, var(--bs-link-opacity, 1));
}

.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='white' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");

  transition: background-image 0.3s ease;
}

.navbar-toggler:hover .navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='RGBA(86, 94, 100, var(--bs-link-opacity, 1))' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");
}
</style>
