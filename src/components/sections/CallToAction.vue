<template>
  <section id="action">
    <div class="container">
      <h2 class="visually-hidden">Call To Action</h2>
      <div class="p-5 text-center">
        <h2 class="">Easy to setup. Easy to maintain</h2>
        <p class="col-lg-8 mx-auto fs-5">
          Bootstrap is a widely-used, sleek, intuitive and powerful front-end
          framework for faster and easier web development.
        </p>
        <div class="d-inline-flex gap-5 mb-5">
          <a
            href="https://www.youtube.com/"
            class="d-inline-flex align-items-center btn btn-danger btn-lg rounded-circle play"
            target="_blank"
            rel="noopener noreferrer"
          >
            <svg class="bi ms-2" width="16" height="16" aria-hidden="true">
              <use href="/sprite.svg#play"></use>
            </svg>
          </a>
          <a
            href="https://getbootstrap.com/"
            class="btn btn-success rounded-pill px-4 py-2"
            target="_blank"
            rel="noopener noreferrer"
            >Get Started</a
          >
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
#action {
  background: linear-gradient(rgba(47, 24, 147, 0.3)),
    url("../../assets/images/call-to-action/call-to-action-background.webp");

  @include background-center;

  @media (-webkit-min-device-pixel-ratio: 2),
    (min-resolution: 192dpi),
    (min-resolution: 2dppx) {
    #action {
      background: linear-gradient(rgba(47, 24, 147, 0.3)),
        url("../../assets/images/call-to-action/call-to-action-background@2x.webp");
    }
  }
}

.play {
  display: block;
}
</style>
