<template>
  <div class="FooterBottom Footer-bottom landing-footer">
    <div class="Footer-bottom-container">
      <div class="Footer-bottom-group">
        <div class="FooterBottomRubriques" v-for="n in 2" :key="n">
            <p class="FooterBottomLinks-title">{{ about.title[n-1] }}</p>
            <ul class="FooterBottomLinks">
                <li class="FooterBottomLinks-item" v-for="i in about.rubriques[n-1].links.length" :key="i">
                    <a :href="about.rubriques[n-1].links[i-1]" class="FooterBottomLinks-link">
                        {{ about.rubriques[n-1].linkTitle[i-1] }}
                    </a>
                </li>
            </ul>
        </div>
      </div>
      <div class="Footer-bottom-group">
        <div class="FooterBottomRubriques" v-for="n in 2" :key="n">
            <p class="FooterBottomLinks-title">{{ social.title[n-1]}}</p>
            <div class="FooterBottomLinks-external">
                <div class="FooterBottomLinks-item" v-for="i in social.rubriques[n-1].links.length" :key="i">
                    <a :href="social.rubriques[n-1].links[i-1]">
                        <img :src="social.rubriques[n-1].linkImg[i-1]" class="FooterBottomLinks-image">
                    </a>
                </div>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
      return {
        name: "FooterBottom",
        about: {
          title: [ "A propos de Trëmma", "Rubriques"],
          rubriques: [{ 
              links: [
                "https://www.tremma.co/qui-sommes-nous","https://www.tremma.co/faire-un-don-tremma",
                "https://www.tremma.co/donner-du-temps","https://www.tremma.co/devenir-partenaire",
                "https://www.tremma.co/politique-de-confidentialite","https://www.tremma.co/cgu"
              ],
              linkTitle: [
                "Qui sommes-nous ?", "Participer financièrement au projet",
                "Donner de mon temps pour un projet", "Devenir partenaire",
                "Politique de confidentialité", "Conditions générales d'utilisation"
              ]},
              { 
                links: [
                  "https://www.tremma.co/projets-actifs", "https://www.tremma.co/c/comment-ca-marche",
                  "https://www.label-emmaus.co/fr/","https://emmaus-france.org/ou-donner-acheter/",
                  "https://service-client.tremma.co/portal/fr/home" 
                ],
                linkTitle: [
                  "Donner un objet",
                  "Comment ça marche ?",
                  "Label Emmaüs",
                  "Points de collecte phyisique",
                  "FAQ - Centre d'aide" 
                ] 
           }]
        },
        social: {
            title: [ "Suivez Trëmma sur", "Ils accompagnent Trëmma" ],
            rubriques: [{ 
              links: [
                "https://www.facebook.com/tremma.co/",
                "https://twitter.com/Tremmaco",
                "https://www.instagram.com/tremma.co/"
              ],
              linkImg: [
                "/svg/facebook.svg",
                "/svg/twitter.svg",
                "/svg/instagram.svg"
              ]},
              { 
              links: [
                  "https://www.accenture.com/fr-fr",
                  "https://www.40-60studio.com",
                  "https://www.wavestone.com/fr/" 
              ],
              linkImg: [
                "/svg/accenture.svg",
                "/svg/40-60.svg",
                "/svg/wavestone.svg"
              ] 
           }]
        }
      }
    }
}
</script>