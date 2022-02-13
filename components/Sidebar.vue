<template>
  <div class="w-1/4 pr-6">
    <accordion>
      <accordion-item v-for="(menu, index) in slideMenu" :key="index">
        <template slot="accordion-link" v-if="!menu.label2">
          <nuxt-link :to="menu.url" class="min-w-full flex items-center">
            <img v-if="menu.icon" :src="menu.icon" alt="" />
            <span class="ml-2">{{ menu.title }}</span>
          </nuxt-link>
        </template>
        <template v-if="menu.label2" slot="accordion-trigger">
        <h3 class="flex items-center justify-between w-full">
            <div class="min-w-max flex items-center">
              <img v-if="menu.icon" :src="menu.icon" alt="">
              <span class="ml-2">{{ menu.title }}</span>
            </div>
            <font-awesome-icon v-if="menu.label2" class="" :icon="['fas', 'fa-chevron-right']"/>
          </h3>
        </template>

        <template v-if="menu.label2" slot="accordion-content">
          <span>lorem2</span>
        </template>
      </accordion-item>
    </accordion>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slideMenu: [
        {
          title: "Vegetables",
          url: "/category/vegetables",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/vegetables.png?v=1644038622",
        },
        {
          title: "Fruits",
          url: "/category/fruits",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/fruits.png?v=1644038622",
          label2: [
            {
              title: "Green Fruits",
              url: "/",
              label3: [
                {
                  title: "Fresh Fruits",
                  url: "/",
                },
                {
                  title: "Frozen Fruits",
                  url: "/",
                },
              ],
            },
            {
              title: "Yellow Fruits",
              url: "/",
            },
            {
              title: "Dry Fruits",
              url: "/",
            },
          ],
        },
        {
          title: "Groceries",
          url: "/",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/groceries.png?v=1644038622",
        },
        {
          title: "Meat",
          url: "/",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/meat.png?v=1644038622",
        },
        {
          title: "Fish",
          url: "/",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/fish.png?v=1644038622",
        },
        {
          title: "Bevarage",
          url: "/",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/bevarage.png?v=1644038622",
        },
        {
          title: "Dry Food",
          url: "/",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/dry-foodood.png?v=1644038622",
        },
      ],
    };
  },
};
</script>
