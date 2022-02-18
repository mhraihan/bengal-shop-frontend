<template>
  <div class="container my-6">
    <div class="flex">
      <Sidebar />
      <div class="w-3/4">
        <SingleBanner
          :padding="banner.padding"
          :titleColor="banner.titleColor"
          :banner="banner"
        />
        <div class="pt-10 mt-10">
          <Title :title="title" />
        </div>
        <CategoryProduct :products="products" />
      </div>
    </div>
  </div>
</template>
<script>
import products from "~/assets/products.json";
export default {
  name: "CategoryPage",
  data() {
    return {
      title: "All Collections",
      products: [],
      banner: {
        bg: "promo-bg-1.png",
        color: "bg-orange-100",
        title: "Up to 30% Discount on Selected Items",
        subTitle: "Buy 1 Get 2",
        padding: "p-12",
        titleColor: "text-green-300",
      },
    };
  },
  created() {
    const id = this.$route.params.id;
    console.log(id);
    if (id) {
      this.title = this.$route.params.id;
      this.products = products.products.filter(
        (p) => p.product_type.toLowerCase() == id.toLowerCase()
      );
    } else {
      this.products = products.products;
    }
  },
};
</script>
