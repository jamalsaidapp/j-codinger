<template>
  <div class="about_inner">
    <div class="left">
      <div class="image">
        <div
          class="main"
          v-scroll-reveal="{ delay: 20 }"
          :style="{ backgroundImage: 'url(' + aboutImg + ')' }"
        ></div>
      </div>
      <!-- End image  -->
    </div>
    <!-- End left -->

    <div class="right">
      <div class="shane_tm_title">
        <span v-scroll-reveal="{ delay: 20 }">À Propos de Moi</span>
        <h3 v-scroll-reveal="{ delay: 40 }">
          Développeur Web Créatif Indépendant basé au Maroc
        </h3>
      </div>
      <div class="text" v-scroll-reveal="{ delay: 60 }">
        <p>
          Je suis un développeur Web indépendant créatif et je suis très passionné et dévoué à mon travail.
          Avec 5 ans d'expérience en tant que développeur web professionnel, j'ai acquis les compétences
          et les connaissances nécessaires pour faire de votre projet un succès. J'apprécie chaque étape du
          processus de conception, de la discussion à la collaboration.
        </p>
      </div>
      <div class="shane_tm_button" v-scroll-reveal="{ delay: 80 }">
        <a href="mailto:said.jamal@j-codinger.com" download>
          Contactez Moi
        </a>
      </div>
    </div>
    <!-- End right -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      aboutImg: require("../../assets/img/about/1.jpg"),
    };
  },
};
</script>
