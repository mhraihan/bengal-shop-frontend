<template>
  <div class="flex items-center justify-center text-4x" :class="text">
    <button class="w-12 h-12 border rounded-full leading-12" :class="border">
      -
    </button>
    <span
      :class="border"
      class="w-12 h-12 mx-6 text-center border rounded-full leading-12"
      >{{ input }}</span
    >
    <button :class="border" class="w-12 h-12 border rounded-full leading-12">
      +
    </button>
  </div>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: "white",
    },
    input: {
      type: String,
      default: "0",
    },
  },
  computed: {
    border() {
      return `border-${this.color}`;
    },
    text() {
      return `text-${this.color}`;
    },
  },
};
</script>
