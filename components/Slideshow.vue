<template>
  <div class="hero-slide">
    <vue-slick-carousel :arrows="false" :dots="true">
      <div class="bg-green-100 rounded-2xl pt-8">
        <div class="container">
          <div class="flex items-center">
            <div class="mr-6 w-1/2 font-size-22">
              <p class="text-green-300 font-size-32 mb-4">Save up 30% off</p>
              <h2 class="text-7xl font-bold text-gray-300 mb-6">
                Bengal Vegetable farm Organic 100%
              </h2>
              <p class="mb-8">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Vehicula faucibus massa est elit maecenas.
              </p>
              <nuxt-link to="/" class="bs-button text-base">Shop Now</nuxt-link>
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
      <div class="bg-green-100 rounded-2xl pt-8">
        <div class="container">
          <div class="flex items-center">
            <div class="mr-6 w-1/2 font-size-22">
              <p class="text-green-300 font-size-32 mb-4">Save up 40% off</p>
              <h2 class="text-7xl font-bold text-gray-300 mb-6">
                Bengal Vegetable farm Organic 100%
              </h2>
              <p class="mb-8">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Vehicula faucibus massa est elit maecenas.
              </p>
              <nuxt-link to="/" class="bs-button text-base">Shop Now</nuxt-link>
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
      <div class="bg-green-100 rounded-2xl pt-8">
        <div class="container">
          <div class="flex items-center">
            <div class="mr-6 w-1/2 font-size-22">
              <p class="text-green-300 font-size-32 mb-4">Save up 50% off</p>
              <h2 class="text-7xl font-bold text-gray-300 mb-6">
                Bengal Vegetable farm Organic 100%
              </h2>
              <p class="mb-8">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Vehicula faucibus massa est elit maecenas.
              </p>
              <nuxt-link to="/" class="bs-button text-base">Shop Now</nuxt-link>
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
