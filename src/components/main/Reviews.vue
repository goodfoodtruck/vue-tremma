<template>
    <div class="Reviews">
        <h2 class="Reviews-title">Les avis de nos donateurs</h2>
        <carousel>
          <div class="swiper-wrapper Slider-slides">
            <carousel-slide v-for="n in slides" :key="n" style="position:relative">
                <p class="Slider-quote">{{ title[n-1] }}
                </p>
                <p class="Slider-firstname">{{ reviewer[n-1] }}</p>
            </carousel-slide>
          </div>
        </carousel>
        <div class="Reviews-bottom">
            <div class="ReviewsWidget ReviewsWidget--secondary">
                <div class="wizville-widget">
                    <div><span class="score">{{ rate }}</span>/5</div>
                    <div class="stars">
                        <span v-for="n in 5" :key="n" class="star" :style="[rating[n-1] ? {background: `url('/svg/star.svg')`} : {background: `url('/svg/starEmpty.svg')`}]"></span>
                    </div>
                    <p class="trustville-legend">
                        <a href="http://trustville.fr/avis-clients/ca/2990/labelemmaus" class="trustville-link">
                        <b>{{ reviews }}</b>
                         avis clients
                        </a>
                    </p>
                </div>
            </div>
            <a href="http://trustville.fr/avis-clients/ca/2990/labelemmaus" class="Reviews-bottomLink Button Button--bordered">
                Lire tous les avis
            </a>
        </div>
    </div>
</template>

<script>
import Carousel from "../carousel/Carousel.vue";
import CarouselSlide from "../carousel/CarouselSlide.vue";

export default {
    data() {
        return {
            name: "Reviews",
            slides: 5,

            title: [
                "Site utile afin de donner une seconde vie aux objets tout en faisant oeuvre de solidarité",
                "Pour le côté participatif. Un peu long à finaliser sans doute objet peu demandé",
                "tout s'est bien passé et j'aime le concept de reverser l'argent à une association tout en permettant à nos vêtements d'avoir une seconde vie",
                "Je suis très satisfait du processus de vente de mon objet: facilité de mise en ligne, vente réalisée en moins de 24 heures et envoi de mon reçu fiscal immédiatement après l'envoi du colis.",
                "Service clair et facile d'utilisation",
            ],

            reviewer: [
                "Florent H.", "Monique A.", "Laurine A.",
                "Alain C.", "A F."
            ],

            reviews: 180,

            rate: 4.6,

            rating: []
        }
    },

    mounted() {
        this.getRate()
    },

    methods: {
        getRate() {
            for (let i = 0; i < 5; i++) {
                if (i>this.rate - 1) {
                    this.rating.push(0)
                } else {
                    this.rating.push(1)
                }
            }
        }
    },
    components: {
        Carousel, CarouselSlide
    }
}
</script>