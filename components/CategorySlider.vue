<template>
  <div class="container pt-20">
    <div class="flex items-center justify-between category-title">
      <h3 class="mb-6 text-4xl text-gray-300">Search by Category</h3>
      <div class="category-arrows min-w-max">
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
      class="mb-10 text-center category-carousel"
      v-bind="categoryCarouselSettings"
      ref="categoryCarousel"
    >
      <div
        v-for="category in categories"
        :key="category.title"
        class="flex flex-col items-center justify-center p-4 text-gray-300 bg-orange-700 cursor-pointer  hover:bg-green-100 category-carousel-item"
      >
        <div class="flex flex-col items-center justify-center mb-4 h-26">
          <img :src="src(category.img)" alt="" />
        </div>
        <h3 class="mb-3 text-xl">{{ category.title }}</h3>
      </div>
    </vue-slick-carousel>
  </div>
</template>
<script>
export default {
  data() {
    return {
      categoryCarouselSettings: {
        slidesToShow: 6,
      },
      categories: [
        {
          img: "carousel-img-1.png",
          title: "Groceries",
          url: "/",
        },
        {
          img: "carousel-img-2.png",
          title: "Fish",
          url: "/",
        },
        {
          img: "carousel-img-3.png",
          title: "Meat",
          url: "/",
        },
        {
          img: "carousel-img-4.png",
          title: "Vegetables",
          url: "/",
        },
        {
          img: "carousel-img-5.png",
          title: "Fruits",
          url: "/",
        },
        {
          img: "carousel-img-6.png",
          title: "Ice Cream",
          url: "/",
        },
        {
          img: "carousel-img-4.png",
          title: "Juice",
          url: "/",
        },
        {
          img: "carousel-img-3.png",
          title: "Chocolate",
          url: "/",
        },
      ],
    };
  },
  methods: {
    src(img) {
      return require(`~/assets/img/${img}`);
    },
    prev() {
      this.$refs.categoryCarousel.prev();
    },
    next() {
      this.$refs.categoryCarousel.next();
    },
  },
};
</script>
