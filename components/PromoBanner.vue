<template>
  <div class="container mt-20">
    <div class="flex -mx-6 mb-14">
      <div
        v-for="(banner, index) in data"
        :key="index"
        :class="width"
        class="flex px-6"
      >
        <SingleBanner :padding="padding" :banner="banner" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array,
      required: true,
    },
    width: {
      type: String,
      default: "w-1/2",
    },
    padding: {
      type: String,
      default: "p-12",
    },
  },
};
</script>

