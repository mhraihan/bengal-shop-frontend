<template>
  <div class="container mt-20">
    <SliderHeader :title="title" :next="next" :prev="prev" />
    <div class="flex items-center mb-10">
      <div style="height: 3px" class="bg-green-500 w-32 h-0.5"></div>
      <div class="bg-gray-800 w-full h-0.5"></div>
    </div>
    <vue-slick-carousel
      class="mb-10 text-center card-carousel"
      v-bind="settings"
      ref="cardCarousel"
    >
      <SingleProduct
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </vue-slick-carousel>
  </div>
</template>
<script>
export default {
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      title: "Deals of the Week",
      settings: {
        slidesToShow: 4,
        dots: false,
        arrows: false,
      },
    };
  },
  methods: {
    prev() {
      this.$refs.cardCarousel.prev();
    },
    next() {
      this.$refs.cardCarousel.next();
    },
  },
};
</script>
