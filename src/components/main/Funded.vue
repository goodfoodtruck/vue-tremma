<template>
<div class="FundedProjects">
  <h2 class="FundedProjects-title">Les projets déjà financés</h2>
  <carousel>
    <div class="swiper-wrapper Slider-slides">
      <carousel-slide v-for="n in slides" :key="n">
          <div class="FundedCard">
            <div class="FundedCard-pics">
              <img :src="'/images/image'+ n +'.jpeg'">
            </div>
            <div class="FundedCard-details">
              <div class="FundedCard-detailsTop">
                <p class="FundedCard-detailsLabel">{{title[n-1]}}</p>
                <p class="FundedCard-detailsDesc">{{ description[n-1] }}</p>
              </div>
              <div class="FundedCard-kpis">
                <div class="FundedCard-kpisItem" v-for="i in 3" :key="i">
                  <div class="Kpi">
                    <p class="Kpi-name">{{ kpiTitle[i-1] }}</p>
                    <p class="Kpi-quote">{{ quote[n-1][i-1] }}</p>
                  </div>
                </div>
              </div>
              <div class="FundedCard-detailsBottom">
                <p class="FundedCard-detailsTitle">Ce projet a été financé par :</p>
                <div class="FundedCard-detailsCard" v-for="x in 2" :key="x">
                  <div class="CardIconText">
                    <img class="CardIconText-icon" :src="'/svg/funded'+ x +'.svg'">
                    <span class="CardIconText-text">{{ funds[n-1][x-1] }}</span>
                  </div>
                </div>
                <div class="FundedCard-detailsCard"></div>
              </div>
              <a href="https://www.tremma.co/projet/ferme-emmaus-baudonne" title class="FundedCard-detailsLinks">Découvrir le projet</a>
            </div>
          </div>
      </carousel-slide>
    </div>
  </carousel>
</div>
</template>

<script>
import Carousel from "../carousel/Carousel.vue";
import CarouselSlide from "../carousel/CarouselSlide.vue";
export default {
    data() {
        return {
            name: "Funded",

            slides: 4,

            title: [
              "Ferme Emmaüs Baudonne", "Ressourcerie du Pays d'Issoire",
              "Ateliers numériques Emmaüs Toulouse", "Emmaüs Connect et les eaux vives"
            ],

            description: [
              "Aidez la Ferme Emmaüs Baudonne en donnant vos objets pour financer un poste de formateur-accompagnateur en numérique qui accompagnera les femmes accueillies à la ferme quelques heures par semaine.",
              `Aidez la ressourcerie du Pays d'Issoire à financer du personnel et du matériel informatique. Grâce à vous, La Ressourcerie du Pays d'Issoire souhaite former 30 bénévoles de leur région au numérique responsable dit "vert" ! Ce projet a pour but d'aider les structures de réemploi et de l'ESS à développer et être plus performantes.`,
              "Aidez la Communauté Emmaüs de Toulouse en donnant vos objets pour financer l'achat de matériel informatique et le salaire du formateur-accompagnant en numérique. Grâce à vous, Emmaüs Toulouse pourra recruter un emploi jeune qui se consacre en majorité aux ateliers numériques et aux démarches sociales pour les compagnons.",
              "Emmaüs Connect, fait de l'inclusion numérique son coeur de métier. Dans le cadre de la campagne Trëmma, c'est l'association les Eaux Vives à Nantes qu'ils ont voulu accompagner. Cette structure souhaite ouvrir un pôle numérique dans le cadre du projet d'écoquartier des ponts à Nantes, pour aider les personnese en situation de grande précarité."
            ],

            kpiTitle: [
              "En bref",
              "Le Projet",
              "La structure"
            ],

            quote: [
              [
                `"La ferme Emmaüs de Baudonne est un lieu d'accompagnement pour des femmes en fin de pein..."`,
                `"La maîtrise de l'outil numérique est un réel atout pour trouver un travail, communiquer..."`,
                `"La Ferme Emmaüs Baudonne, crée en 2018, se situe à quelques kilomètres de Bayonne, au..."`
              ], [
                `La Ressourcerie du Pays d'Issoire collecte chaque année 140 tonnes d'objets, dont 90% s..."`,
                `"La Ressourcerie est très impliquée dans le tissu associatif de la région Auvergne. Le b..."`,
                `"Lancée en août 2016 par Louise et Guillaume Benoit, la Ressourcerie a pour coeur d'activ..."`
              ], [
                `"Emmaüs Toulouse est l'une des plus grandes communautés Emmaüs de France, qui accueille..."`,
                `"La communauté souhaite lutter contre la facture numérique dont sont victimes les compa..."`,
                `"La communauté Emmaüs de Toulouse a été créée en 1977 et regroupe désormais 3 sites en r..."`
              ], [
                `"Emmaüs Connect lutte contre l'exclusion numérique des plus fragiles et veut désormais t..."`,
                `"L'objectif est de permettre à des publics isolés d'accélerer leur parcours d'insertion..."`,
                `"Depuis plus de 7 ans, Emmaüs Connect, association du mouvement Emmaüs, fait de l'inclus..."`
              ]
            ],

            funds: [
              [260,1712], [199,1340], [321,1776], [242,1574]
            ]
            
        }
    },
    components: { 
      Carousel,
      CarouselSlide
      } 
    
}
</script>