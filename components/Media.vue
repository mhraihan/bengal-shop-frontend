<template>
  <div class="w-1/4 px-4 flex items-center">
    <div class="min-w-max mr-4">
      <img :src="src" loading="lazy" width="80" />
    </div>
    <div class="w-full">
      <h3 class="text-xl font-medium mb-2">{{ title }}</h3>
      <p class="mb-0">{{ text }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    img: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
  },
  computed: {
    src() {
      return require(`~/assets/img/${this.img}`);
    },
  },
};
</script>
