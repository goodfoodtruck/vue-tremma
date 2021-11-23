<template>
  <transition :name="transition">
    <div class="swiper-slide Slider-slide" v-show="visible" style="position:fixed">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
    };
  },
  computed: {
    transition() {
      return "slide-" + this.$parent.direction;
    },

    visible() {
      return this.index === this.$parent.index;
    },
  },
};
</script>

<style>
.slide-right-enter-active {
  animation: slideRightIn 0.5s;
}

.slide-right-leave-active {
  animation: slideRightOut 0.5s;
}

.slide-left-enter-active {
  animation: slideLeftIn 0.5s;
}

.slide-left-leave-active {
  animation: slideLeftOut 0.5s;
}

@keyframes slideRightIn {
  from {
    transform: translateX(100%);
    opacity: 0
  }
  to {
    transform: translateX(0);
    opacity: 1
  }
}

@keyframes slideRightOut {
  from {
    transform: translateX(0);
    opacity: 1
  }
  to {
    transform: translateX(-100%);
    opacity: 0
  }
}

@keyframes slideLeftIn {
  from {
    transform: translateX(-100%);
    oapcit: 0
  }
  to {
    transform: translateX(0);
    opacity: 1
  }
}

@keyframes slideLeftOut {
  from {
    transform: translateX(0);
    opacity: 1
  }
  to {
    transform: translateX(100%);
    opacity: 0
  }
}
</style>