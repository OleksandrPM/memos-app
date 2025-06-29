<script setup>
import FeatureCard from "../FeatureCard.vue";
import features from "../../content/features/features.json";
</script>

<template>
  <section id="features">
    <h2 class="visually-hidden">Features</h2>
    <div class="row">
      <div class="col-4 d-none d-md-block">
        <img
          src="../../assets/images/features/Mockup.png"
          alt="laptop"
          class="mockup"
        />
      </div>

      <div class="col-md-7">
        <div class="d-flex flex-column align-items-start gap-2">
          <h2 class="fw-bold text-body-emphasis">We Create Something New</h2>
          <p class="text-body-secondary">
            We have created a new product that will help designers, developers
            and companies create websites for their startups quickly and easily.
          </p>
        </div>
        <div class="col">
          <div class="row row-cols-1 row-cols-sm-2 g-4">
            <FeatureCard
              :name="features[0].name"
              :description="features[0].description"
              :badgePath="features[0].badgePath"
              :badgeWidth="features[0].badgeWidth"
              :badgeHeight="features[0].badgeHeight"
            />
            <FeatureCard
              :name="features[1].name"
              :description="features[1].description"
              :badgePath="features[1].badgePath"
              :badgeWidth="features[1].badgeWidth"
              :badgeHeight="features[1].badgeHeight"
            />
            <!-- <div class="col d-flex flex-column gap-2">
              <div
                class="feature-icon-small d-inline-flex align-items-center text-bg-primary bg-gradient fs-4 rounded-3"
              >
                <svg class="bi" width="38" height="38" aria-hidden="true">
                  <use href="../../assets/squares.svg"></use>
                </svg>
              </div>
              <h4 class="fw-semibold mb-0 text-body-emphasis">
                30 New feature pages
              </h4>
              <p class="text-body-secondary">
                Startup Framework contains components and complex blocks which
                can easily.
              </p>
            </div>
            <div class="col d-flex flex-column gap-2">
              <div
                class="feature-icon-small d-inline-flex align-items-center text-bg-primary bg-gradient fs-4 rounded-3"
              >
                <svg class="bi" width="44" height="35" aria-hidden="true">
                  <use href="../../assets/diamond.svg"></use>
                </svg>
              </div>
              <h4 class="fw-semibold mb-0 text-body-emphasis">
                Useful Symbol Components
              </h4>
              <p class="text-body-secondary">
                Samples will show you the feeling on how to play around using
                the components.
              </p>
            </div>
            <div class="col d-flex flex-column gap-2">
              <div
                class="feature-icon-small d-inline-flex align-items-center text-bg-primary bg-gradient fs-4 rounded-3"
              >
                <svg class="bi" width="44" height="35" aria-hidden="true">
                  <use href="../../assets/diamond.svg"></use>
                </svg>
              </div>
              <h4 class="fw-semibold mb-0 text-body-emphasis">
                Featured title
              </h4>
              <p class="text-body-secondary">
                Paragraph of text beneath the heading to explain the heading.
              </p>
            </div>
            <div class="col d-flex flex-column gap-2">
              <div
                class="feature-icon-small d-inline-flex align-items-center text-bg-primary bg-gradient fs-4 rounded-3"
              >
                <svg class="bi" width="38" height="38" aria-hidden="true">
                  <use href="../../assets/squares.svg"></use>
                </svg>
              </div>
              <h4 class="fw-semibold mb-0 text-body-emphasis">
                Featured title
              </h4>
              <p class="text-body-secondary">
                Paragraph of text beneath the heading to explain the heading.
              </p>
            </div> -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
#features {
  position: relative;

  padding-top: 6.25rem;
  padding-bottom: 6.25rem;

  background: linear-gradient(rgba(47, 24, 147, 0.5)),
    url("../../assets/images/features/features-background.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

@media (-webkit-min-device-pixel-ratio: 2),
  (min-resolution: 192dpi),
  (min-resolution: 2dppx) {
  #features {
    background: linear-gradient(rgba(47, 24, 147, 0.5)),
      url("../../assets/images/features/features-background.jpg");
  }
}

.mockup {
  width: 100%;
}
</style>
