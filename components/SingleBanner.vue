<template>
  <div
    :class="`${banner.color} ${padding}`"
    class="flex items-center justify-between w-full bg-center bg-cover rounded  promo-bg-1"
    :style="style(banner.bg)"
  >
    <div class="w-1/2">
      <p v-if="banner.subTitle" class="mb-6 text-2xl text-orange-500">
        {{ banner.subTitle }}
      </p>
      <h3 class="mb-8 font-bold leading-tight font-size-46" :class="titleColor">
        {{ banner.title }}
      </h3>
      <nuxt-link
        v-if="banner.label"
        :to="banner.url"
        :class="
          banner.label
            ? 'bs-button-white'
            : 'h-12 w-12 flex justify-center items-center rounded-full bg-white hover:bg-orange-500 text-orange-500 hover:text-white scale-100 hover:scale-105 nuxt-link-exact-active nuxt-link-active transition-all'
        "
      >
        <span v-if="banner.label"> {{ banner.label }}</span>
        <font-awesome-icon
          v-else
          class=""
          :icon="['fas', 'long-arrow-alt-right']"
        />
      </nuxt-link>
    </div>
    <div class="flex justify-end w-1/2" v-if="banner.img">
      <img
        class="w-3/4"
        :src="src(banner.img)"
        :alt="banner.title"
        loading="lazy"
      />
    </div>
  </div>
</template>
<script>
export default {
  props: {
    banner: {
      type: Object,
      required: true,
    },
    padding: {
      type: String,
      default: "p-12",
    },
    titleColor: {
      type: String,
      default: "text-gray-400",
    },
  },
  data() {
    return {};
  },
  methods: {
    src(img) {
      return require(`~/assets/img/${img}`);
    },
    style(img) {
      return img ? `background-image: url(${this.src(img)})` : "";
    },
  },
};
</script>
