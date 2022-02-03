<template>
  <div class="single-bs-product">
    <div
      class="flex flex-col items-center justify-center p-4 text-gray-300 cursor-pointer  card-carousel-item"
    >
      <div class="relative mb-4 h-50">
        <div class="flex flex-col items-center justify-center h-full p-0">
          <img
            :class="`${height} ${width}`"
            :src="src(product.images[0].src)"
            alt=""
          />
        </div>
        <div
          class="absolute top-0 left-0 flex flex-col items-center justify-center w-full h-full  product-img-hover"
        >
          <div class="w-full h-full bg-black opacity-60"></div>
          <button
            class="absolute bottom-0 left-0 z-20 flex items-center justify-center w-full p-2 bg-gray-100 rounded-t-lg  text-gray-1000"
          >
            <span>Details</span>
            <font-awesome-icon
              class="ml-2"
              :icon="['fas', 'long-arrow-alt-right']"
            />
          </button>
          <div
            class="absolute z-10 flex items-center justify-center w-full h-full"
          >
            <div
              class="flex items-center justify-center mb-8 text-4xl text-white"
            >
              <button
                class="w-12 h-12 border border-white rounded-full leading-12"
              >
                -
              </button>
              <span
                class="w-12 h-12 mx-6 border border-white rounded-full  leading-12"
                >0</span
              >
              <button
                class="w-12 h-12 border border-white rounded-full leading-12"
              >
                +
              </button>
            </div>
          </div>
        </div>
      </div>
      <h3 v-if="product.vendor" class="mb-3 text-sm font-normal text-gray-600">
        {{ product.vendor }}
      </h3>
      <h3 v-if="product.title" class="mb-3 text-xl font-bold">
        {{ product.title }}
      </h3>
      <div class="flex justify-center product-price">
        <span class="text-orange-500">${{ product.variants[0].price }}</span>
        <span
          v-if="product.variants[0].compare_at_price"
          class="ml-2 text-gray-600 line-through"
          >${{ product.variants[0].compare_at_price }}</span
        >
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Object,
      required: true,
    },
    width: {
      type: String,
      default: "w-auto",
    },
    height: {
      type: String,
      default: "h-auto",
    },
  },
  data() {
    return {};
  },
  methods: {
    src(img) {
      return img;
    },
  },
};
</script>
<style lang="scss" scoped>
.product-img-hover {
  display: none;
}
.single-bs-product:hover .product-img-hover {
  display: flex;
}
</style>



