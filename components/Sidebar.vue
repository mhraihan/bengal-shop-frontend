<template>
  <div class="w-1/4 mr-6">
    <div class="border border-green-100">
      <accordion :activeState="false">
        <accordion-item :accordion__content="'py-6 px-4'">
          <template slot="accordion-trigger">
            <div class="w-full p-4 bg-green-100">
              <h3
                class="
                  flex
                  items-center
                  justify-between
                  w-full
                  hover:text-green-500
                "
              >
                <div class="flex items-center min-w-max">
                  <span class="ml-2">Categories</span>
                </div>
                <font-awesome-icon
                  class="hover:text-green-500"
                  :icon="['fas', 'fa-chevron-right']"
                />
              </h3>
            </div>
          </template>
          <template slot="accordion-content">
            <accordion>
              <accordion-item v-for="(menu, index) in slideMenu" :key="index">
                <template slot="accordion-link" v-if="!menu.label">
                  <nuxt-link
                    :to="menu.url"
                    class="flex items-center min-w-full hover:text-green-500"
                  >
                    <img v-if="menu.icon" :src="menu.icon" alt="" />
                    <span class="ml-2">{{ menu.title }}</span>
                  </nuxt-link>
                </template>
                <template v-if="menu.label" slot="accordion-trigger">
                  <h3
                    class="
                      flex
                      items-center
                      justify-between
                      w-full
                      font-normal
                      hover:text-green-500
                    "
                  >
                    <div class="flex items-center min-w-max">
                      <img v-if="menu.icon" :src="menu.icon" alt="" />
                      <span class="ml-2">{{ menu.title }}</span>
                    </div>
                    <font-awesome-icon
                      v-if="menu.label"
                      class="hover:text-green-500"
                      :icon="['fas', 'fa-chevron-right']"
                    />
                  </h3>
                </template>

                <template v-if="menu.label" slot="accordion-content">
                  <accordion>
                    <accordion-item
                      v-for="(child, index) in menu.label"
                      :key="index"
                    >
                      <template slot="accordion-link" v-if="!child.label">
                        <nuxt-link
                          :to="child.url"
                          class="
                            flex
                            items-center
                            min-w-full
                            hover:text-green-500
                          "
                        >
                          <span class="ml-2">{{ child.title }}</span>
                        </nuxt-link>
                      </template>
                      <template v-if="child.label" slot="accordion-trigger">
                        <h3
                          class="
                            flex
                            items-center
                            justify-between
                            w-full
                            font-normal
                            hover:text-green-500
                          "
                        >
                          <div class="flex items-center min-w-max">
                            <span class="ml-2">{{ child.title }}</span>
                          </div>
                          <font-awesome-icon
                            v-if="child.label"
                            class="hover:text-green-500"
                            :icon="['fas', 'fa-chevron-right']"
                          />
                        </h3>
                      </template>
                      <template v-if="child.label" slot="accordion-content">
                        <accordion-item
                          v-for="(grandChild, index) in child.label"
                          :key="index"
                        >
                          <template slot="accordion-link">
                            <nuxt-link
                              :to="grandChild.url"
                              class="
                                flex
                                items-center
                                min-w-full
                                hover:text-green-500
                              "
                            >
                              <span class="ml-2">{{ grandChild.title }}</span>
                            </nuxt-link>
                          </template>
                        </accordion-item>
                      </template>
                    </accordion-item>
                  </accordion>
                </template>
              </accordion-item>
            </accordion>
          </template>
        </accordion-item>
      </accordion>
    </div>
  </div>
</template>

<script>
import accordionItem from "./accordion-item.vue";
export default {
  components: { accordionItem },
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
          label: [
            {
              title: "Green Fruits",
              url: "/category/green-fruits",
              label: [
                {
                  title: "Fresh Fruits",
                  url: "/category/fresh-fruits",
                },
                {
                  title: "Frozen Fruits",
                  url: "/category/frozen-fruits",
                },
              ],
            },
            {
              title: "Yellow Fruits",
              url: "/category/yellow-fruits",
            },
            {
              title: "Dry Fruits",
              url: "/category/dry-fruits",
            },
          ],
        },
        {
          title: "Groceries",
          url: "/category/groceries",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/groceries.png?v=1644038622",
        },
        {
          title: "Meat",
          url: "/category/meat",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/meat.png?v=1644038622",
        },
        {
          title: "Fish",
          url: "/category/fish",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/fish.png?v=1644038622",
        },
        {
          title: "Bevarage",
          url: "/category/bevarage",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/bevarage.png?v=1644038622",
        },
        {
          title: "Dry Food",
          url: "/category/dry-food",
          icon: "https://cdn.shopify.com/s/files/1/0530/6849/7053/files/dry-foodood.png?v=1644038622",
        },
      ],
    };
  },
};
</script>
