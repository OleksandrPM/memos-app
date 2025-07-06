<template>
  <footer class="section">
    <h2 class="visually-hidden">Footer</h2>
    <div class="container">
      <div class="top-line d-flex align-items-center justify-content-between">
        <h3>Startup 3</h3>
        <div class="links d-flex">
          <ul class="privacy list-unstyled d-flex">
            <li>
              <a
                class="text-reset text-decoration-none"
                href="#"
                target="_blank"
                rel="noopener noreferrer"
                >Privacy Policy</a
              >
            </li>
            <li>
              <a
                class="text-reset text-decoration-none"
                href="#"
                target="_blank"
                rel="noopener noreferrer"
                >Terms</a
              >
            </li>
          </ul>
          <ul class="socials d-flex">
            <li>
              <a
                class="text-reset text-decoration-none"
                href="https://x.com/"
                target="_blank"
                rel="noopener noreferrer"
              >
                <svg width="39" height="32">
                  <use href="/sprite.svg#twitter"></use>
                </svg>
              </a>
            </li>
            <li>
              <a
                class="text-reset text-decoration-none"
                href="https://www.facebook.com/"
                target="_blank"
                rel="noopener noreferrer"
              >
                <svg width="18" height="32">
                  <use href="/sprite.svg#facebook"></use>
                </svg>
              </a>
            </li>
            <li>
              <a
                class="text-reset text-decoration-none"
                href="https://www.google.com/"
                target="_blank"
                rel="noopener noreferrer"
              >
                <svg width="48" height="32">
                  <use href="/sprite.svg#google-plus"></use>
                </svg>
              </a>
            </li>
          </ul>
        </div>
      </div>
      <div
        class="bottom-line d-flex align-items-center justify-content-between"
      >
        <nav>
          <ul class="list-unstyled d-flex">
            <li>
              <a class="text-reset text-decoration-none" href="#features"
                >Features</a
              >
            </li>
            <li>
              <a class="text-reset text-decoration-none" href="#pricing"
                >Pricing Plans</a
              >
            </li>
            <li>
              <a class="text-reset text-decoration-none" href="#">Our Works</a>
            </li>
            <li>
              <a class="text-reset text-decoration-none" href="#">Brands</a>
            </li>
            <li>
              <a class="text-reset text-decoration-none" href="#contact"
                >Contacts</a
              >
            </li>
          </ul>
        </nav>
        <p>© 2025. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
.section {
  @media screen and (min-width: $bp-tablet-width) {
    padding-top: 4.94rem;
    padding-bottom: 4.46rem;
  }
}

li,
p {
  @include font-16;
}

a {
  transition: opacity 0.3s ease;

  &:hover {
    opacity: 0.4;
  }
}

.top-line {
  flex-direction: column;
  row-gap: 3rem;
  padding-bottom: 4.1rem;

  border-bottom: 0.2rem solid rgba($color-pricing-border, 0.3);

  @media screen and (min-width: $bp-tablet-width) {
    flex-direction: row;
  }

  & h3 {
    @include font-24;
  }

  & .links {
    flex-direction: column;
    gap: 3rem;

    @media screen and (min-width: $bp-tablet-width) {
      flex-direction: row;
    }
  }

  & .privacy {
    column-gap: 2.7rem;
  }

  & .socials {
    column-gap: 2.9rem;
    justify-content: center;

    & svg {
      width: auto;
      height: 1.6rem;
    }
  }
}

.bottom-line {
  flex-direction: column;
  row-gap: 3rem;
  padding-top: 4.74rem;

  @media screen and (min-width: $bp-tablet-width) {
    flex-direction: row;
  }

  & ul {
    flex-wrap: wrap;
    gap: 2.7rem;
    justify-content: center;
  }
}
</style>
