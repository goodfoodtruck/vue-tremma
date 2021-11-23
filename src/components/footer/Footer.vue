<template>
  <footer class="Footer">
    <div class="Footer-top">
      <div class="Reinsurance">
        <p class="Reinsurance-title">Nos garanties</p>
        <a href="https://tremma.co/garanties" class="Reinsurance-link">
          <ul class="Reinsurance-list">
            <li class="Reinsurance-listItem" v-for="n in 4" :key="n">
              <img src="/svg/validation.svg" class="Reinsurance-validation" />
              {{ title[n - 1] }}
            </li>
          </ul>
        </a>
      </div>
    </div>

    <div class="newsletterInscription">
        <div class="newsletterInscription-container">
            <div class="newsletterInscription-texts">
                <div class="newsletterInscription-title">
                    <span>S'inscrire à la newsletter</span>
                </div>
                <div class="newsletterInscription-text">
                    <p>Inscrivez-vous à la newsletter pour suivre l'actualité de Trëmma et des projets soutenus et recevoir nos bons plans.</p>
                </div>
            </div>
            <div class="newsletterInscription-form">
                <div id="newsletter-Form">
                    <form class="validate">
                        <div class="mc-field-group">
                            <input type="text" placeholder="Votre nom" class="newsletterInscription-inputfields">
                        </div>
                        <div class="mc-field-group">
                            <input type="text" placeholder="Votre email" class="newsletterInscription-inputfields">
                        </div>
                        <div class="newsletterInscription-formtext content__gdpr mc-field-group">
                            <p>Vos coordonnées sont uniquement utilisés pour vous envoyer les newsletters Trëmma. Vous pouvez à tout moment utiliser le lien de 
                                désabonnement intégré dans la newsletter.
                            <a class="newsletterInscription-link">En savoir plus sur la gestion de vos données et vos droits</a>
                            </p>
                        </div>
                        <div class="clear">
                            <input type="submit" value="S'inscrire" class="Form-submitButton button">
                        </div>
                    </form>
                </div>
          </div>
        </div>
    </div>

    <footer-bottom></footer-bottom>
   <div class="Sticky-faq">
    <div class="Sticky-faq-button">
      <img src="/svg/faq.svg">
    </div>
   </div>
    <div class="Sticky-blog">
      <div class="Sticky-blog-container">
        <a href="https://blog.tremma.co/" class="Sticky-blog-button">
          Blog Trëmma
          <img src="/svg/foreign-white.svg">
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
import FooterBottom from './FooterBottom.vue';
export default {
  components: { FooterBottom },
  data() {
    return {
      name: "Footer",
      title: [" Solidarité", " Transparence", " Sécurité", " Simplicité"],
    };
  },
};
</script>