<template>
  <div class="container pt-20">
    <div class="flex items-center justify-between card-title">
      <h3 class="mb-6 text-4xl text-gray-300">
        {{ data.title }}
      </h3>
      <div class="card-arrows min-w-max">
        <button
          @click="prev"
          class="w-8 h-8 p-1 mr-4 transition-all rounded-full  arrow-left hover:bg-green-500 hover:text-white"
        >
          <font-awesome-icon class="" :icon="['fas', 'chevron-left']" />
        </button>
        <button
          @click="next"
          class="w-8 h-8 p-1 transition-all rounded-full  arrow-right hover:bg-green-500 hover:text-white"
        >
          <font-awesome-icon class="" :icon="['fas', 'chevron-right']" />
        </button>
      </div>
    </div>
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
          <img class="h-full" :src="src(card.img)" alt="" />
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
