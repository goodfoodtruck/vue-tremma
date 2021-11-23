<template>
  <main class="Main">
    
    <div class="Slider--home">
      <Home />
    </div>

    <section class="u-Section-bgWhite">
      <div class="HowToSteps">
        <h2 class="HowToSteps-title">Comment ça marche ?</h2>
        <ul class="HowToSteps-list">
          <li class="HowToSteps-listItem" v-for="n in 6" :key="n">
            <img class="HowToSteps-listItem-image" :src="'/images/etape' + n + '.png'" />
            <h3 class="HowToSteps-listItem-title">Etape {{ n }}</h3>
            <p class="HowToSteps-listItem-text">{{ howtoTitle[n - 1] }}</p>
          </li>
        </ul>
      </div>
    </section>

    <section class="u-Section-bgBlueLight--onlyDesktop">
      <section class="ActiveProjects ActiveProjects--home">
        <div class="ActiveProjects-container">
          <h2 class="ActiveProjects-title ActiveProjects-title--onlyDesktop">Les projets à soutenir</h2>
          <ul class="ProjectsList">
            <li class="ProjectsList-item" v-for="n in 4" :key="n">
              <div class="ProjectCard">
                <div class="ProjectCard-content">
                  <p class="ProjectCard-contentTitle">{{ project.title[n - 1] }}</p>
                  <div class="ProjectCard-contentProgress">Financement
                    <br />
                    <span class="ProjectCard-contentProgressValue">à {{ project.progress[n-1] }} %
                      <span class="ProjectCard-content-ProgressValueDetails"> en objets vendus</span>
                    </span>
                    <span class="Progressbar">
                      <span class="Progressbar-value" style="max-width: 100%" :style="'width:'+ project.progress[n-1] +'%'"></span>
                    </span>
                  </div>
                  <p class="ProjectCard-contentDate">Fin le : 10 janv. 2022</p>
                  <a class="ProjectCard-contentLink Button Button--primary Button--small" :href="'https://tremma.co/projet/' + project.link[n - 1]">Découvrir le projet</a>
                </div>
                <div class="ProjectCard-pics">
                  <img class="ProjectCard-picsImg" :src="'/images/Emmaus-' + n + '.jpeg'" />
                </div>
              </div>
            </li>
          </ul>
          <div class="ActiveProjects-actions">
            <a class="ActiveProjects-actionsLink Button Button--bordered" href="https://tremma.co/projets">Voir tous les projets</a>
          </div>
        </div>
      </section>
    </section>

    <div class="u-Section-bgWhite--onlyDesktop">
      <Funded />
    </div>

    <div class="u-Section-bgBlueLight--onlyDesktop">
      <Reviews />
    </div>

    <div class="u-Section-bgWhite Support">
      <div class="Support-container">
        <h2 class="Support-title">Soutenir Trëmma</h2>
        <div class="Support-body">
          <div class="Support-item" v-for="n in 3" :key="n">
            <div :style="'background-image: url(/images/support'+ n +'.jpg);'"></div>
            <div>
              <p>{{ support.title[n-1]}}</p>
              <div>
                <a :href="support.link[n-1]" class="Button Button--primary Button--small">{{ support.linkTitle[n - 1] }}</a>
              </div>
            </div>
          </div>
          <div class="Support-item-noimage">
            <p>N'hésitez pas à suivre et partager nos actualités sur les réseaux sociaux</p>
            <div class="Support-item-socialIcons">
              <a href="https://www.facebook.com/tremma.co/">
                <img src="/svg/facebook.svg" class="Support-item-socialIcon">
              </a>
              <a href="https://twitter.com/Tremmaco">
                <img src="/svg/twitter.svg" class="Support-item-socialIcon">
              </a>
              <a href="https://www.instagram.com/tremma.co/">
                <img src="/svg/instagram.svg"  class="Support-item-socialIcon">
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import Home from "./Home.vue"
import Funded from "./Funded.vue"
import Reviews from "./Reviews.vue"


export default {
  data() {
    return {
      name: "Main",

      howtoTitle: [
        "Choisissez avec amour l'objet que vous souhaitez donner.",
        "Sélectionnez le projet qui bénéficiera de la vente de votre objet.",
        "Renseignez le plus précisément possible les caractéristiques du produit.",
        "Votre objet est acheté sur label-emmaüs.co.",
        "Déposez votre objet en point relais ou choisissez une remise en main propre.",
        "L'argent de la vente est reversé au projet que vous aviez choisi!",
      ],

      project: {
        title: [
          "Le numérique au service de l'insertion chez Emmaüs défi",
          '"Métamorphose" par la recyclerie sportive : 3ème vie du sport',
          "Emmaüs alternatives s'engage pour l'inclusion numérique !",
          "Seconde vie des ordinateurs avec Emmaüs 53",
        ],
        link: [
          "le-numerique-au-service-de-l-insertion-chez-emmaus-defi",
          "metamorphose-par-la-recyclerie-sportive-3eme-vie-du-sport",
          "emmaus-alternatives-s-engage-pour-l-inclusion-numerique",
          "seconde-vie-des-ordinateurs-avec-emmaus-53",
        ],
        progress: [ 40, 12, 68, 94]
      },
      
      support: {
        title: [
          "Contribuez à développer et pérenniser Trëmma à votre échelle",
          "Apportez votre aide sur un projet de transition solidaire et écologique",
          "Engagez votre entreprise au côté d'un projet associatif",
        ],
        link: [
          "https://www.tremma.co/faire-un-don-tremma",
          "https://www.tremma.co/donner-du-temps",
          "https://www.tremma.co/devenir-partenaire",
        ],
        linkTitle: [
          "Participer financièrement au projet",
          "Donner de mon temps pour un projet",
          "Devenir partenaire",
        ],
      },
    };
  },
  components: {
    Home,
    Funded,
    Reviews
  },
};
</script>