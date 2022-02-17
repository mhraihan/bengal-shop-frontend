<template>
  <div class="flex flex-wrap mb-10 category-products">
    <div v-for="product in products" :key="product.id" class="w-1/3">
      <SingleProduct :product="product" />
    </div>
  </div>
</template>
<script>
export default {
  props: {
    products: Array,
    required: true,
  },
};
</script>
