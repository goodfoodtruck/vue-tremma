<template>
  <div class="carousel swiper-container Slider swiper-container-initialized swiper-container-horizontal">
    <slot></slot>
    <div v-if="slidesCount < 4" class="Slider-dots swiper-pagination-clickable swiper-pagination-bullets carousel__pagination">
      <button v-for="n in slidesCount" :key="n" @click="goto(n - 1)" class="Slider-dot" :class="{ active: n - 1 == index }"></button>
    </div>
    <div v-if="slidesCount > 3" class="Slider-arrows">
      <button class="Slider-arrow Slider-arrow Slider-arrow--left"
        @click.prevent="prev">
        <img src="/images/prev.png" class="Slider-arrow-icon">
      </button>
      <button class="Slider-arrow Slider-arrow Slider-arrow--right"
        @click.prevent="next">
        <img src="/images/next.png" class="Slider-arrow-icon">
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
      slides: [],
      direction: "",
    };
  },
  mounted() {
    this.slides = this.$children;
    this.slides.forEach((slide, i) => {
      slide.index = i;
    });
  },
  computed: {
    slidesCount() {
      return this.slides.length;
    },
  },
  methods: {
    next() {
      this.index++;
      this.direction = "right";
      if (this.index >= this.slidesCount) {
        this.index = 0;
      }
    },
    prev() {
      this.index--;
      this.direction = "left";
      if (this.index < 0) {
        this.index = this.slidesCount - 1;
      }
    },
    goto(index) {
      this.direction = index > this.index ? "right" : "left";
      this.index = index;
    },
  },
};
</script>

<style>
</style>