<template>
  <div>
    <div class="container">
      <div class="flex items-center justify-between py-6">
        <div class="w-1/4">
          <Logo />
        </div>

        <div class="w-3/4 pl-20">
          <div class="flex items-center justify-between">
            <div class="flex w-full pl-10">
              <div
                class="flex items-center justify-center w-3/4 px-1 py-1 border border-gray-100 rounded-full "
              >
                <div class="px-3 miw-w-max">
                  <img
                    src="~/assets/img/search.png"
                    loading="lazy"
                    alt="search icon"
                    srcset=""
                  />
                </div>
                <input
                  type="search"
                  placeholder="Search here..."
                  class="w-full px-3 py-1 focus:outline-none"
                />
                <button
                  type="submit"
                  class="px-6 py-2 text-white bg-gray-400 rounded-full  bs-button-bg"
                >
                  Search
                </button>
              </div>
            </div>
            <div class="flex items-center min-w-max">
              <nuxt-link to="/">
                <span
                  class="flex items-center justify-center rounded-full  bs-icon-box hover:bg-gray-200"
                >
                  <img
                    src="~/assets/img/heart.png"
                    loading="lazy"
                    alt="heart icon"
                    srcset=""
                  />
                </span>
              </nuxt-link>
              <nuxt-link to="/" class="relative mx-4">
                <span
                  class="flex items-center justify-center rounded-full  bs-icon-box hover:bg-gray-200"
                >
                  <img
                    src="~/assets/img/cart.png"
                    loading="lazy"
                    alt="cart icon"
                    srcset=""
                  />
                </span>
                <span
                  class="absolute top-0 right-0 flex items-center justify-center w-4 h-4 text-xs text-white bg-orange-600 rounded-full "
                  >0</span
                >
              </nuxt-link>
              <nuxt-link to="/" class="flex items-center">
                <span
                  class="flex items-center justify-center rounded-full  bs-icon-box hover:bg-gray-200"
                >
                  <img
                    src="~/assets/img/account.png"
                    loading="lazy"
                    alt="account icon"
                    srcset=""
                  />
                </span>
                <span>Account</span>
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>

      <div class="flex items-center">
        <div
          v-click-outside="onClickOutside"
          class="relative w-1/4 header-slide-menu"
        >
          <div
            @click="toogleMenu"
            :class="menuOpen ? 'menu-open' : ''"
            class="relative z-20 flex items-center px-4 py-2 bg-green-300 rounded-full cursor-pointer "
          >
            <div class="min-w-max">
              <img
                src="~/assets/img/menu-right.png"
                loading="lazy"
                alt="menu"
                srcset=""
              />
            </div>
            <div class="w-full text-center text-white">All Categories</div>
            <div class="min-w-max menu-down-icon">
              <img
                src="~/assets/img/chevron-down.png"
                loading="lazy"
                alt="down"
                srcset=""
              />
            </div>
          </div>
          <div
            class="absolute z-10 w-full pt-8 pb-1 -mt-5 bg-green-300  rounded-b-xl"
            v-if="menuOpen"
          >
            <ul class="vega-menu">
              <li
                class="menu-link"
                v-for="(menu, index) in slideMenu"
                :key="index"
              >
                <nuxt-link
                  :to="menu.url"
                  class="block px-8 py-2 text-white  link-title hover:text-black hover:bg-green-200"
                >
                  <div class="alink">{{ menu.title }}</div>
                </nuxt-link>
              </li>
            </ul>
          </div>
        </div>
        <div class="flex items-center justify-between w-3/4 pl-20">
          <div class="w-full">
            <ul class="flex">
              <li v-for="(menu, index) in mainMenu" :key="index">
                <nuxt-link
                  :to="menu.url"
                  class="px-6 py-4 hover:text-green-300"
                  >{{ menu.title }}</nuxt-link
                >
              </li>
            </ul>
          </div>
          <nuxt-link to="/" class="flex items-center text-orange-600 min-w-max">
            <img
              src="~/assets/img/percentage.png"
              loading="lazy"
              alt="down"
              srcset=""
            />
            <span class="ml-3">Speical Offers</span>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menuOpen: false,
      mainMenu: [
        {
          title: "Home",
          url: "/",
        },
        {
          title: "Categories",
          url: "/category",
        },
        {
          title: "About",
          url: "/about",
        },
        {
          title: "Contact",
          url: "/",
        },
        {
          title: "FAQs",
          url: "/",
        },
        {
          title: "Offers",
          url: "/",
        },
      ],
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
  methods: {
    toogleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    onClickOutside(event) {
      this.menuOpen = false;
      console.log("Clicked outside. Event: ", event);
    },
  },
};
</script>

<style lang="scss" scoped>
.menu-down-icon {
  .menu-open & {
    transform: rotate(180deg);
  }
  transition: 0.25s;
}
</style>
