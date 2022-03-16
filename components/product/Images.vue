<template>
  <div class="product-img">
    <div class="main-image">
      <vue-slick-carousel v-bind="settings">
        <div class="main-image-list" v-for="img in images" :key="img.id">
          <img :src="img.src" alt="" srcset="" />
        </div>
      </vue-slick-carousel>
    </div>
    <div class="thumbnails"></div>
  </div>
</template>
<script>
export default {
  props: {
    images: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      settings: {
        dots: false,
        arrows: true,
        dotsClass: "slick-dots custom-dot-class",
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        lazyLoad: "ondemand",
      },
    };
  },
};
</script>

<style lang="scss" scoped>
/* dirty hack for enable carousel swipe */
.main-image-list {
  pointer-events: none;
}
</style>
