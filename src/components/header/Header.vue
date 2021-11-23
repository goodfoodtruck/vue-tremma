<template>
  <header class="Header">
    <div class="Header-container">
      <button class="Header-action">
        <span class="Header-actionBurger">
          <span class="Header-actionBurgerLine"></span>
        </span>
      </button>
      <h1 class="Header-logo">
        <img src="/svg/logo-tremma-emmaus.svg" alt="Trëmma" class="Header-logoImg" />
      </h1>
      <ul class="Header-menu">
        <li class="Header-menuItem">
          <a href="https://www.tremma.co/qui-sommes-nous" class="Header-menuLink">Qui sommes-nous ?</a>
        </li>
        <li class="Header-menuItem">
          <a href="https://www.tremma.co/c/comment-ca-marche" class="Header-menuLink" >Comment ça marche ?</a>
        </li>
        <li class="Header-menuItem">
          <a href="https://www.label-emmaus.co/fr/" class="Header-menuLink">
            Acheter un objet
            <img src="/svg/foreign.svg" alt="Foreign link" class="Foreign-logo" />
          </a>
        </li>
        <li class="Header-menuItem">
          <a href="https://www.tremma.co/projets-actifs" class="Header-menuLink-special">
          Donner un objet
          </a>
        </li>
      </ul>
      <button class="Header-guest">
        <a href="https://www.tremma.co/mon-compte" class="Header-guestCobutton">
          Connexion
        </a>
      </button>
    </div>

    <LayerMenu />
  </header>
</template>

<script>
import LayerMenu from "./LayerMenu.vue"

export default {
  name: "Header",
  components: { LayerMenu }
};
</script>
