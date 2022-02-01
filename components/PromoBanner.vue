<template>
  <div class="container mt-20">
    <div class="flex -mx-6 mb-14">
      <div class="w-1/2 px-6">
        <div class="p-12 bg-center bg-cover rounded promo-bg-1">
          <div class="w-1/2">
            <p class="mb-6 text-2xl text-orange-500">Buy 1 Get 1</p>
            <h3 class="mb-8 font-bold leading-tight font-size-46">
              Fresh Fruits Collection
            </h3>
            <nuxt-link to="/" class="bs-button-white">Order Now</nuxt-link>
          </div>
        </div>
      </div>
      <div class="w-1/2 px-6">
        <div class="p-12 bg-center bg-cover rounded promo-bg-2">
          <div class="w-1/2">
            <p class="mb-6 text-2xl text-orange-500">Buy 1 Get 1</p>
            <h3 class="mb-8 font-bold leading-tight font-size-46">
              Fresh Fruits Collection
            </h3>
            <nuxt-link to="/" class="bs-button-white">Order Now</nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style  scoped>
.promo-bg-1 {
  background-image: url(../assets/img/promo-bg-1.png);
}
.promo-bg-2 {
  background-image: url(../assets/img/promo-bg-2.png);
}
</style>
