<template>
  <div class="min-h-full">
    <div class="p-8">
      <Slideshow />
      <CardSlider :data="categories" />
      <PromoBanner />
      <CardSlider :data="brands" />
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
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
    };
  },
};
</script>
