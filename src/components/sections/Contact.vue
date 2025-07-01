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
  <section id="contact" class="py-5">
    <h2 class="visually-hidden">Contact</h2>
    <div class="container px-5 py-5">
      <div class="row">
        <div class="col">
          <h3>Let’s Keep in Touch</h3>
          <p>
            We have created a new product that will help designers, developers
            and companies create websites for their startups quickly and easily.
          </p>
          <address class="d-flex flex-column align-items-start gap-2">
            <a href="tel:+15555055050">+1 555 505 5050</a>
            <a href="mailto:info@designmodo.com">info@designmodo.com</a>
            <p>
              San Francisco, CA560 Bush St & 20th Ave, Apt5 San Francisco,
              <br />
              230909
            </p>
          </address>
        </div>
        <div class="col">
          <form
            class="contact100-form validate-form needs-validation d-flex flex-column gap-3"
            ref="formRef"
            @submit.prevent="handleSubmit"
          >
            <div class="row d-flex justify-content-between">
              <div class="col-sm-6">
                <label for="firstName" class="form-label">YOUR NAME</label>
                <input
                  type="text"
                  class="form-control rounded-pill"
                  id="firstName"
                  name="firstName"
                  placeholder="First name"
                  value=""
                  required
                  autocomplete="name"
                />
                <div class="invalid-feedback">
                  Valid first name is required.
                </div>
              </div>
              <div class="col-sm-5">
                <label for="budget" class="form-label">BUDGET</label>
                <select
                  class="form-select rounded-pill"
                  id="budget"
                  name="budget"
                >
                  <option value="500">$500</option>
                  <option value="1000">$1000</option>
                  <option value="1500">$1500</option>
                  <option value="2000">$2000</option>
                  <option value="2500">$2500</option>
                  <option value="3000">$3000</option>
                </select>
              </div>
            </div>
            <div class="row">
              <div class="col">
                <label for="email" class="form-label">YOUR EMAIL</label>
                <input
                  type="email"
                  class="form-control rounded-pill"
                  id="email"
                  name="email"
                  placeholder="name@mail.com"
                  value=""
                  required
                  autocomplete="email"
                />
                <div class="invalid-feedback">Valid email is required.</div>
              </div>
            </div>
            <div class="row">
              <div class="col">
                <label for="message" class="form-label">MESSAGE</label>
                <textarea
                  id="message"
                  name="message"
                  class="form-control rounded-3"
                  placeholder="Message"
                  rows="3"
                  required
                  wrap="hard"
                ></textarea>
              </div>
            </div>

            <div class="d-flex justify-content-between">
              <div class="">
                <input
                  class="input-checkbox100"
                  id="ckb1"
                  name="copy-mail"
                  type="checkbox"
                />
                <label class="label-checkbox100" for="ckb1">
                  Send me a copy
                </label>
              </div>
              <button
                class="btn btn-success rounded-pill contact100-form-btn"
                type="submit"
              >
                Send
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
#contact {
  background: linear-gradient(rgba(47, 24, 147, 0.5)),
    url("../../assets/images/contact/contact-background.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

@media (-webkit-min-device-pixel-ratio: 2),
  (min-resolution: 192dpi),
  (min-resolution: 2dppx) {
  #contact {
    background: linear-gradient(rgba(47, 24, 147, 0.5)),
      url("../../assets/images/contact/contact-background.jpg");
  }
}
</style>
