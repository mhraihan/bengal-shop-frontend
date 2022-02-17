<template>
  <h3 class="mb-6 text-4xl text-gray-300">
    {{ title }}
  </h3>
</template>

<script>
export default {
  props: {
    title: String,
    required: true,
  },
};
</script>
