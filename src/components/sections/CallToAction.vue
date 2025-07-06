<template>
  <section id="action" class="section">
    <h2 class="visually-hidden">Call To Action</h2>
    <div class="container d-flex flex-column align-items-center">
      <h3 class="title text-center">
        Easy to setup.<br />
        Easy to maintain
      </h3>
      <p class="text text-center">
        Bootstrap is a widely-used, sleek, intuitive and powerful front-end
        framework for faster and easier web development.
      </p>
      <div class="buttons">
        <a
          href="https://www.youtube.com/"
          class="play"
          target="_blank"
          rel="noopener noreferrer"
          title="Go to Youtube"
        >
          <svg class="icon" width="16" height="18" aria-hidden="true">
            <use href="/sprite.svg#play"></use>
          </svg>
        </a>
        <a
          href="https://getbootstrap.com/"
          class="button"
          target="_blank"
          rel="noopener noreferrer"
          title="Go to Bootstrap"
          >Get Started</a
        >
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

.title {
  margin-bottom: 2rem;

  @include font-58;

  @media screen and (min-width: $bp-tablet-width) {
    margin-bottom: 2rem;
    width: 77rem;
  }
}

.text {
  margin-bottom: 5.8rem;

  @include font-base;

  @media screen and (min-width: $bp-tablet-width) {
    margin-bottom: 5.8rem;
    width: 48rem;
  }
}

.buttons {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3rem;

  @media screen and (min-width: $bp-tablet-width) {
    flex-direction: row;
  }
}

.play {
  position: relative;
  width: 5rem;
  height: 5rem;

  border-radius: 50%;
  background-color: $color-youtube;

  transition: opacity 0.3s ease;

  @media screen and (min-width: $bp-tablet-width) {
    width: 7rem;
    height: 7rem;
  }

  &:hover {
    opacity: 0.7;
  }

  & .icon {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-40%, -40%);
  }
}

.button {
  height: 5rem;
  padding-left: 3rem;
  padding-right: 3rem;

  @include font-20;
  line-height: 5rem;
  vertical-align: middle;
  border-radius: 10rem;

  color: inherit;
  background-color: $color-primary-btn;

  transition: opacity 0.3s ease;

  @media screen and (min-width: $bp-tablet-width) {
    height: 7rem;
    padding-left: 5.2rem;
    padding-right: 5.2rem;
    line-height: 7rem;
  }

  &:hover {
    opacity: 0.7;
  }
}
</style>
