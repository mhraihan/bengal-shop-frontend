<template>
  <div class="min-h-full">
    <div class="p-8">
      <Slideshow />
      <CardSlider :data="categories" />
      <PromoBanner :data="banners" />
      <ProductCarousel :products="products" />
      <CardSlider :data="brands" width="w-3/5" height="h-auto" />
      <PromoBanner :data="banners2" width="w-1/3" padding="p-6" />
    </div>
  </div>
</template>

<script>
import products from "~/assets/products.json";
export default {
  name: "IndexPage",
  head() {
    return {
      title: "Home",
    };
  },
  data() {
    return {
      products: [],
      categories: {
        title: "Search by Category",
        class: "bg-orange-700 hover:bg-green-100",
        settings: {
          slidesToShow: 6,
          dots: false,
          arrows: false,
        },
        data: [
          {
            img: "carousel-img-1.png",
            title: "Groceries",
            url: "/",
          },
          {
            img: "carousel-img-2.png",
            title: "Fish",
            url: "/",
          },
          {
            img: "carousel-img-3.png",
            title: "Meat",
            url: "/",
          },
          {
            img: "carousel-img-4.png",
            title: "Vegetables",
            url: "/",
          },
          {
            img: "carousel-img-5.png",
            title: "Fruits",
            url: "/",
          },
          {
            img: "carousel-img-6.png",
            title: "Ice Cream",
            url: "/",
          },
          {
            img: "carousel-img-4.png",
            title: "Juice",
            url: "/",
          },
          {
            img: "carousel-img-3.png",
            title: "Chocolate",
            url: "/",
          },
        ],
      },
      brands: {
        title: "Popular Brands",
        settings: {
          slidesToShow: 6,
          dots: false,
          arrows: false,
        },
        data: [
          {
            img: "brand-1.png",
            url: "/",
          },
          {
            img: "brand-2.png",

            url: "/",
          },
          {
            img: "brand-3.png",

            url: "/",
          },
          {
            img: "brand-4.png",

            url: "/",
          },
          {
            img: "brand-5.png",

            url: "/",
          },
          {
            img: "brand-6.png",

            url: "/",
          },
          {
            img: "brand-4.png",

            url: "/",
          },
          {
            img: "brand-3.png",

            url: "/",
          },
        ],
      },
      banners: [
        {
          bg: "promo-bg-1.png",
          color: "bg-orange-100",
          title: "Vegetable Collection",
          subTitle: "Buy 1 Get 2",
          label: "Order Now",
          url: "/",
        },
        {
          bg: "promo-bg-2.png",
          color: "bg-orange-100",
          title: "Fresh Fruits Collection",
          subTitle: "Buy 1 Get 1",
          label: "Order Now",
          url: "/",
        },
      ],
      banners2: [
        {
          img: "fresh-fruit.png",
          color: "bg-yellow-900",
          title: "Fruits Collection",
          url: "/",
        },
        {
          img: "vegetable-collection.png",
          color: "bg-green-400",
          title: "Vegetable Collection",
          url: "/",
        },
        {
          img: "grocery-items.png",
          color: "bg-yellow-800",
          title: "Grocery Item",
          url: "/",
        },
      ],
    };
  },
  created() {
    // console.log(products);
    this.products = products.products.slice(0, 8);
  },
};
</script>
