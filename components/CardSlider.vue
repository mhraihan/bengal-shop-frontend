<template>
  <div class="container mt-20">
    <SliderHeader :title="data.title" :next="next" :prev="prev" />
    <div class="flex items-center mb-10">
      <div style="height: 3px" class="bg-green-500 w-32 h-0.5"></div>
      <div class="bg-gray-800 w-full h-0.5"></div>
    </div>
    <vue-slick-carousel
      class="mb-10 text-center card-carousel"
      v-bind="data.settings"
      ref="cardCarousel"
    >
      <div
        v-for="(card, index) in data.data"
        :key="index"
        class="flex flex-col items-center justify-center p-4 text-gray-300 cursor-pointer  card-carousel-item"
        :class="data.class"
      >
        <div class="flex flex-col items-center justify-center h-24 mb-4">
          <img :class="`${height} ${width}`" :src="src(card.img)" alt="" />
        </div>
        <h3 v-if="card.title" class="mb-3 text-xl">{{ card.title }}</h3>
      </div>
    </vue-slick-carousel>
  </div>
</template>
<script>
export default {
  props: {
    data: {
      type: Object,
      required: true,
    },
    width: {
      type: String,
      default: "w-auto",
    },
    height: {
      type: String,
      default: "h-full",
    },
  },
  data() {
    return {};
  },
  methods: {
    src(img) {
      return require(`~/assets/img/${img}`);
    },
    prev() {
      this.$refs.cardCarousel.prev();
    },
    next() {
      this.$refs.cardCarousel.next();
    },
  },
};
</script>
