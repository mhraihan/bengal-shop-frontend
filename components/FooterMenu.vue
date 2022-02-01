<template>
  <div class="w-1/5 pl-6">
    <h3 class="text-2xl mb-6">{{ title }}</h3>
    <ul class="leading-loose">
      <li v-for="link in links" :key="link">
        <nuxt-link :to="link.url">{{ link.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    links: {
      required: true,
      type: Array,
    },
  },
};
</script>
