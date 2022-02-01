<template>
  <div>
    <div class="container">
      <div class="flex flex-wrap justify-between items-center py-6">
        <Logo />
        <div class="w-96">
          <div
            class="
              border border-gray-100
              px-1
              py-1
              flex
              rounded-full
              items-center
            "
          >
            <div class="miw-w-max px-3">
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
              class="bg-gray-400 px-6 py-2 bs-button-bg rounded-full text-white"
            >
              Search
            </button>
          </div>
        </div>
        <div class="min-w-max flex items-center">
          <nuxt-link to="/">
            <span
              class="
                bs-icon-box
                rounded-full
                hover:bg-gray-200
                flex
                items-center
                justify-center
              "
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
              class="
                bs-icon-box
                rounded-full
                hover:bg-gray-200
                flex
                items-center
                justify-center
              "
            >
              <img
                src="~/assets/img/cart.png"
                loading="lazy"
                alt="cart icon"
                srcset=""
              />
            </span>
            <span
              class="
                absolute
                bg-orange-600
                w-4
                h-4
                top-0
                right-0
                rounded-full
                text-xs text-white
                flex
                justify-center
                items-center
              "
              >0</span
            >
          </nuxt-link>
          <nuxt-link to="/" class="flex items-center">
            <span
              class="
                bs-icon-box
                rounded-full
                hover:bg-gray-200
                flex
                items-center
                justify-center
              "
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
        <div class="w-96">
          <div
            class="
              bg-green-300
              rounded-full
              px-4
              py-2
              cursor-pointer
              flex
              items-center
            "
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
            <div class="min-w-max">
              <img
                src="~/assets/img/chevron-down.png"
                loading="lazy"
                alt="down"
                srcset=""
              />
            </div>
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
        <nuxt-link to="/" class="min-w-max text-orange-600 flex items-center">
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
