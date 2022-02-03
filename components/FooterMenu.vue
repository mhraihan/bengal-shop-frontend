<template>
  <div class="w-1/5 pl-6">
    <h3 class="mb-6 text-2xl">{{ title }}</h3>
    <ul class="leading-loose">
      <li v-for="(link, index) in links" :key="index">
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
