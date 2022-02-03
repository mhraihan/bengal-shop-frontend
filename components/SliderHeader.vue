<template>
  <div ref="cardCarousel" class="flex items-center justify-between card-title">
    <h3 class="mb-6 text-4xl text-gray-300">
      {{ title }}
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
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    prev: {
      type: Function,
      required: true,
    },
    next: {
      type: Function,
      required: true,
    },
  },
};
</script>
