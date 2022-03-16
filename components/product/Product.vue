<template>
  <div class="single-bs-product">
    <div
      class="
        flex flex-col
        items-center
        justify-center
        p-4
        text-gray-300
        cursor-pointer
        card-carousel-item
      "
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
          class="
            absolute
            top-0
            left-0
            flex flex-col
            items-center
            justify-center
            w-full
            h-full
            product-img-hover
          "
        >
          <div
            @click.prevent="open(product)"
            class="w-full h-full bg-black opacity-60"
          ></div>
          <button
            @click.prevent="open(product)"
            class="
              absolute
              bottom-0
              left-0
              z-20
              flex
              items-center
              justify-center
              w-full
              p-2
              bg-gray-100
              rounded-t-lg
              text-gray-1000
            "
          >
            <span>Details</span>
            <font-awesome-icon
              class="ml-2"
              :icon="['fas', 'long-arrow-alt-right']"
            />
          </button>
          <div
            class="
              absolute
              z-10
              flex
              items-center
              justify-center
              w-full
              h-full
              mb-8
            "
          >
            <LazyInput />
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
import QuickView from "~/components/quickview";

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
    open(product) {
      this.$modal.show(
        QuickView,
        {
          text: "This text is passed as a property lol",
          product,
        },
        {
          width: 1000,
          height: "auto",
        }
      );
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



