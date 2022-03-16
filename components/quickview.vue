<template>
  <div class="quick-view">
    <!-- Pin to top right corner -->

    <div class="absolute top-0 right-0 h-12 w-12">
      <a
        class="
          hover:bg-orange-600
          transition-all
          flex
          h-full
          items-center
          justify-center
          hover:text-white
        "
        href="#"
        @click.prevent="$emit('close')"
        ><font-awesome-icon class="" :icon="['fas', 'times']"
      /></a>
    </div>

    <div class="flex h-full">
      <div class="w-1/2 p-8">
        <LazyImages :images="product.images" />
      </div>
      <div class="w-1/2 p-8">
        <div class="product-details">
          <p class="text-sm mb-3">
            <span class="uppercase text-gray-600 pr-6">Status</span>
            <span class="text-green-300">In Stock</span>
          </p>
          <h3 class="text-2xl">{{ product.title }}</h3>

          <p class="text-2xl font-bold mt-4 mb-2">
            ${{ product.variants[0].price }}
            <del
              v-if="product.variants[0].compare_at_price"
              class="font-normal text-gray-600"
              >${{ product.variants[0].compare_at_price }}</del
            >
          </p>
          <div
            class="
              flex
              border-b border-gray-200
              justify-between
              text-sm
              pb-3
              mb-8
            "
          >
            <p class="text-xs text-gray-600 mt-0">
              <b>{{ getRandomIntInclusive() }}</b> items available.
            </p>
          </div>

          <div class="flex justify-between items-center my-4">
            <p class="font-medium uppercase">Quantity</p>
            <div class="flex">
              <LazyInput :color="'black'" input="1" />
            </div>
          </div>
          <div class="flex my-6">
            <button class="bs-button w-full">Add to cart</button>
          </div>
          <div
            class="
              flex
              border-b border-gray-200
              justify-between
              text-sm
              pb-3
              mb-8
            "
          >
            <p class="flex items-center">
              <img src="~/assets/img/heart.png" class="w-4 mr-3" alt="" /> Add
              to Wishlist
            </p>
            <p class="flex items-center">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-4 w-4 mr-3"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z"
                />
              </svg>
              Share
            </p>
          </div>
          <div class="text-xs leading-loose">
            <p v-if="product.variants[0].sku" class="mb-2">
              <span class="text-sm uppercase text-gray-600 w-28 inline-block"
                >Sku:</span
              >
              <span class="text-sm"> {{ product.variants[0].sku }} </span>
            </p>
            <p class="mb-2">
              <span class="uppercase text-sm text-gray-600 w-28 inline-block"
                >category:</span
              >

              <span class="text-sm">
                <nuxt-link
                  class="bs-dark-green-color"
                  :to="'/category/' + product.product_type"
                  >{{ product.product_type }}
                </nuxt-link>
              </span>
            </p>

            <p>
              <span class="uppercase text-sm text-gray-600 w-28 inline-block"
                >Tags:</span
              >

              <span
                class="text-sm"
                v-for="(item, index) in product.tags"
                :key="index"
              >
                <span v-if="index !== 0" class="comma">, </span>

                <nuxt-link
                  class="bs-dark-green-color"
                  :to="'/category/' + item"
                  >{{ item.split("_")[1] }}</nuxt-link
                >
              </span>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "QuickView",
  props: {
    text: {
      type: String,
      default: null,
    },
    product: {
      type: Object,
      required: true,
    },
  },
  methods: {
    getRandomIntInclusive(min = 5, max = 100) {
      min = Math.ceil(min);
      max = Math.floor(max);
      return Math.floor(Math.random() * (max - min + 1) + min); //The maximum is inclusive and the minimum is inclusive
    },
  },
  created() {
    console.log(this.product);
  },
};
</script>
