<template>
  <div class="hero-slide">
    <vue-slick-carousel :arrows="false" :dots="true">
      <div class="pt-8 bg-green-100 rounded-2xl">
        <div class="container">
          <div class="flex items-center">
            <div class="w-1/2 mr-6 font-size-22">
              <p class="mb-4 text-green-300 font-size-32">Save up 30% off</p>
              <h2 class="mb-6 font-bold text-gray-300 font-size-70">
                Bengal Vegetable farm Organic 100%
              </h2>
              <p class="mb-8">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Vehicula faucibus massa est elit maecenas.
              </p>
              <nuxt-link to="/" class="text-base bs-button">Shop Now</nuxt-link>
            </div>
            <div class="flex justify-end w-1/2">
              <img
                width="550"
                src="~/assets/img/hero.png"
                loading="lazy"
                alt=""
                srcset=""
              />
            </div>
          </div>
        </div>
      </div>
      <div class="pt-8 bg-green-100 rounded-2xl">
        <div class="container">
          <div class="flex items-center">
            <div class="w-1/2 mr-6 font-size-22">
              <p class="mb-4 text-green-300 font-size-32">Save up 40% off</p>
              <h2 class="mb-6 font-bold text-gray-300 text-7xl">
                Bengal Vegetable farm Organic 100%
              </h2>
              <p class="mb-8">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Vehicula faucibus massa est elit maecenas.
              </p>
              <nuxt-link to="/" class="text-base bs-button">Shop Now</nuxt-link>
            </div>
            <div class="flex justify-end w-1/2">
              <img
                width="550"
                src="~/assets/img/hero.png"
                loading="lazy"
                alt=""
                srcset=""
              />
            </div>
          </div>
        </div>
      </div>
      <div class="pt-8 bg-green-100 rounded-2xl">
        <div class="container">
          <div class="flex items-center">
            <div class="w-1/2 mr-6 font-size-22">
              <p class="mb-4 text-green-300 font-size-32">Save up 50% off</p>
              <h2 class="mb-6 font-bold text-gray-300 text-7xl">
                Bengal Vegetable farm Organic 100%
              </h2>
              <p class="mb-8">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Vehicula faucibus massa est elit maecenas.
              </p>
              <nuxt-link to="/" class="text-base bs-button">Shop Now</nuxt-link>
            </div>
            <div class="flex justify-end w-1/2">
              <img
                width="550"
                src="~/assets/img/hero.png"
                loading="lazy"
                alt=""
                srcset=""
              />
            </div>
          </div>
        </div>
      </div>
    </vue-slick-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>
<style scoped>
</style>
