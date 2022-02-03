<template>
  <div>
    <div class="container">
      <div class="flex flex-wrap items-center justify-between py-6">
        <Logo />
        <div class="w-96">
          <div
            class="flex items-center px-1 py-1 border border-gray-100 rounded-full "
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
              class="px-6 py-2 text-white bg-gray-400 rounded-full bs-button-bg"
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

      <div class="flex items-center">
        <div
          v-click-outside="onClickOutside"
          class="relative w-96 header-slide-menu"
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
        <div class="w-full">
          <ul class="flex justify-center">
            <li>
              <nuxt-link to="/" class="p-4">Home</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/" class="p-4">Categories</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/" class="p-4">About</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/" class="p-4">Contact</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/" class="p-4">FAQs</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/" class="p-4">Offers</nuxt-link>
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
</template>
<script>
export default {
  data() {
    return {
      menuOpen: false,
      slideMenu: [
        {
          title: "Fresh Vegetable",
          url: "/",
        },
        {
          title: "Fresh Fruits",
          url: "/",
        },
        {
          title: "Cow Milk",
          url: "/",
        },
        {
          title: "Fresh Meat",
          url: "/",
        },
        {
          title: "Green Dhaniya",
          url: "/",
        },
        {
          title: "Haldi Powder",
          url: "/",
        },
        {
          title: "Mag Almoner",
          url: "/",
        },
        {
          title: "Ice Cream",
          url: "/",
        },
        {
          title: "Sea & Fish",
          url: "/",
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
