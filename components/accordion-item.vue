<template>
  <li class="accordion__item">
    <div class="accordion__item--link">
      <slot name="accordion-link"></slot>
    </div>
    <div
      class="accordion__trigger"
      :class="{ accordion__trigger_active: visible }"
      @click="open"
    >
      <!-- This slot will handle the title/header of the accordion and is the part you click on -->
      <slot name="accordion-trigger"></slot>
    </div>

    <transition
      name="accordion"
      @enter="start"
      @after-enter="end"
      @before-leave="start"
      @after-leave="end"
    >
      <div
        class="accordion__content"
        :class="accordion__content"
        v-show="visible"
      >
        <ul>
          <!-- This slot will handle all the content that is passed to the accordion -->
          <slot name="accordion-content"></slot>
        </ul>
      </div>
    </transition>
  </li>
</template>


<script>
export default {
  props: {
    accordion__content: {
      type: String,
      default: "relative mt-4 before",
    },
  },
  inject: ["Accordion"],
  data() {
    return {
      index: null,
    };
  },
  computed: {
    visible() {
      return this.index == this.Accordion.active;
    },
  },
  methods: {
    open() {
      if (this.visible) {
        this.Accordion.active = null;
      } else {
        this.Accordion.active = this.index;
      }
    },
    start(el) {
      el.style.height = el.scrollHeight + "px";
    },
    end(el) {
      el.style.height = "";
    },
  },
  created() {
    this.index = this.Accordion.count++;
  },
};
</script>

<style lang="scss" scoped>
.accordion__item {
  cursor: pointer;
  padding: 0px;
  position: relative;
  .accordion__content {
    .accordion__item {
      padding: 10px;
    }
  }
}

.accordion__trigger {
  display: flex;
  justify-content: space-between;
  &.accordion__trigger_active {
    svg {
      transform: rotate(90deg);
    }
  }
  svg {
    padding: 0 5px;
    transition: transform 0.3s ease;
  }
}

.accordion-enter-active,
.accordion-leave-active {
  will-change: height, opacity;
  transition: height 0.3s ease, opacity 0.3s ease;
  overflow: hidden;
}

.accordion-enter,
.accordion-leave-to {
  height: 0 !important;
  opacity: 0;
}
.accordion__content.before {
  padding-left: calc(35px / 2);
  &:before {
    content: "";
    width: 1px;
    height: 100%;
    background: #e0e0e0;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }
  .accordion__item {
    padding-right: 0;
  }
}
</style>
