<script setup lang="ts">
import { ref } from "vue";

const formRef = ref<HTMLFormElement | null>(null);

const handleSubmit = (e: Event) => {
  const formEl = e.target as HTMLFormElement;
  const formData = new FormData(formEl);
  const data = Object.fromEntries(formData.entries());

  const resultString = Object.entries(data)
    .map(([key, value]) => `${key} - ${value}`)
    .join(", ");

  alert(`You send the next data: ${resultString}`);

  formRef.value?.reset();
};
</script>

<template>
  <section id="contact" class="section">
    <h2 class="visually-hidden">Contact</h2>
    <div class="container">
      <div class="address-block">
        <h3>Let’s Keep in Touch</h3>
        <p>
          We have created a new product that will help designers, developers and
          companies create websites for their startups quickly and easily.
        </p>
        <address class="d-flex flex-column align-items-start">
          <a href="tel:+15555055050">
            <svg class="icon phone-icon" width="15" height="15">
              <use href="/sprite.svg#fa-phone"></use>
            </svg>
            +1 555 505 5050
          </a>
          <a href="mailto:info@designmodo.com">
            <svg class="icon phone-icon" width="19" height="15">
              <use href="/sprite.svg#fa-envelope"></use>
            </svg>
            info@designmodo.com
          </a>
          <a
            href="https://maps.app.goo.gl/kwkzwspTrgtKvbGb8"
            target="_blank"
            ref="noopener noreferrer"
          >
            <svg class="icon phone-icon" width="15" height="19">
              <use href="/sprite.svg#fa-building"></use>
            </svg>
            <div>
              San Francisco, CA560 Bush St &<br />
              20th Ave, Apt5 San Francisco,
              <br />
              230909
            </div>
          </a>
        </address>
      </div>
      <form
        class="form validate-form needs-validation d-flex flex-column"
        ref="formRef"
        @submit.prevent="handleSubmit"
      >
        <div class="d-flex justify-content-between">
          <div class="name-thumb">
            <label for="firstName" class="form-label">YOUR NAME</label>
            <input
              type="text"
              class="form-control"
              id="firstName"
              name="firstName"
              placeholder="First name"
              value=""
              required
              autocomplete="name"
            />
            <div class="invalid-feedback">Valid first name is required.</div>
          </div>
          <div class="budget-thumb">
            <label for="budget" class="form-label">BUDGET</label>
            <select class="form-select" id="budget" name="budget">
              <option value="500">$500</option>
              <option value="1000">$1000</option>
              <option value="1500">$1500</option>
              <option value="2000">$2000</option>
              <option value="2500">$2500</option>
              <option value="3000">$3000</option>
            </select>
          </div>
        </div>
        <label for="email" class="form-label">YOUR EMAIL</label>
        <input
          type="email"
          class="form-control"
          id="email"
          name="email"
          placeholder="name@mail.com"
          value=""
          required
          autocomplete="email"
        />
        <div class="invalid-feedback">Valid email is required.</div>

        <label for="message" class="form-label">YOUR MESSAGE</label>
        <textarea
          id="message"
          name="message"
          class="form-control"
          placeholder="Message"
          rows="3"
          required
          wrap="hard"
        ></textarea>

        <div class="d-flex justify-content-between">
          <div class="d-flex align-items-center">
            <input
              class="input-checkbox"
              id="ckb1"
              name="copy-mail"
              type="checkbox"
            />
            <label class="label-checkbox" for="ckb1"> Send me a copy </label>
          </div>
          <button class="btn contact-form-btn" type="submit">Send</button>
        </div>
      </form>
    </div>
  </section>
</template>

<style scoped lang="scss">
#contact {
  background: linear-gradient(rgba(47, 24, 147, 0.4)),
    url("../../assets/images/contact/contact-background.webp");

  @include background-center;

  @media (-webkit-min-device-pixel-ratio: 2),
    (min-resolution: 192dpi),
    (min-resolution: 2dppx) {
    #contact {
      background: linear-gradient(rgba(47, 24, 147, 0.4)),
        url("../../assets/images/contact/contact-background@2x.webp");
    }
  }

  @media screen and (min-width: $bp-tablet-width) {
    padding-left: 21.5rem;
    padding-right: 21.5rem;
  }
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  @media screen and (max-width: calc($bp-tablet-width - 0.02px)) {
    gap: 3rem;
  }

  @media screen and (min-width: $bp-tablet-width) {
    flex-direction: row;
  }
}

.address-block {
  @media screen and (min-width: $bp-tablet-width) {
    width: 41rem;
  }

  & h3 {
    margin-bottom: 2.8rem;

    @include font-42;
  }

  & p {
    margin-bottom: 5.3rem;

    @include font-base;
  }

  & address {
    gap: 3.2rem;

    & a {
      display: flex;
      align-items: baseline;

      @include font-16;

      & .icon {
        margin-right: 1.5rem;
      }
    }
  }
}

.form {
  border-radius: 1rem;

  color: $color-input;
  background-color: $color-form-bkg;

  @media screen and (min-width: $bp-tablet-width) {
    width: 47rem;
    padding: 5.8rem 5rem 5.6rem 5rem;
  }

  & .name-thumb {
    width: 20rem;
  }

  & .budget-thumb {
    width: 14rem;
  }

  & input,
  & select,
  & textarea {
    @include font-18;

    color: $color-input;
    border: 0.2rem solid $color-input-border;

    &::placeholder {
      color: $color-input-placeholder;
      opacity: 0.4;
    }
  }

  & input:not(.input-checkbox),
  & select {
    margin-bottom: 3.5rem;
    height: 5rem;
    padding-left: 2.4rem;
    padding-right: 2.4rem;

    border-radius: 10rem;
  }

  & textarea {
    margin-bottom: 3rem;
    padding: 1.3rem 1.9rem;

    resize: none;
    border-radius: 1rem;
  }

  & .form-label {
    margin-bottom: 0.6rem;

    font-family: $font-bold;
    @include font-14;
  }

  & .form-control {
    &::placeholder {
      @include font-18;
    }
  }

  & .input-checkbox {
    margin-bottom: 0;
    margin-right: 1.2rem;
    appearance: none;
    width: 2rem;
    height: 2rem;

    border: 2px solid $color-input-border;
    border-radius: 0.6rem;

    cursor: pointer;

    transition: border 0.3s ease, background-color 0.3s ease;

    &:hover {
      border: none;
      background-color: $color-primary-btn;
    }

    &:checked {
      background-color: $color-primary-btn;

      &::after {
        content: "✔";
        color: $color-input;
        font-size: 1.6rem;
        position: relative;
        left: 2px;
        top: -3px;
      }
    }
  }

  & .label-checkbox {
    @include font-16;

    color: $color-input-placeholder;
    opacity: 0.4;
  }

  & .contact-form-btn {
    width: 12rem;
    height: 5rem;

    @include font-18;
    border-radius: 10rem;

    color: $color-text-main;
    background-color: $color-primary-btn;

    transition: opacity 0.3s ease;

    &:hover {
      opacity: 0.6;
    }
  }
}
</style>
