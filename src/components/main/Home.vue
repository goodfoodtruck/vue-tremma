<template>
    <div>
      <carousel>
        <div class="swiper-wrapper Slider-slides">
          <carousel-slide v-for="n in slides" :key="n">
            <div class="Slider-container">
              <h2 class="Slider-title">{{ title[n - 1] }}</h2>
            </div>
            <div class="Slider-bg" :style="`background: url('/svg/emmaus-` + n + `.svg')`"></div>
          </carousel-slide>
        </div>
        <div class="Slider-button Slider-button">
          <a href="https://tremma.co/projets-actifs" class="Button Button--primary">Donner un objet</a>
        </div>
      </carousel>
    </div>
</template>

<script>
import Carousel from '../carousel/Carousel.vue'
import CarouselSlide from '../carousel/CarouselSlide.vue'

export default {
    data() {
        return {
            name: 'Home',

            slides: 3,

            title: [
                "Vous avez envie de faire du tri ? Profitez en pour soutenir un projet solidaire !",
                "Sur Trëmma, créez une annonce en quelques clics pour donner une seconde vie à votre objet.",
                "L'argent de la vente permettra au projet de votre choix de voir le jour !",
            ],
        }
    },
    components: {
      Carousel,
      CarouselSlide
    }
}
</script>