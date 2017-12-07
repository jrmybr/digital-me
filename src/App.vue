<template>
  <div id="app">
      <app-nav></app-nav>
      <app-header></app-header>
      <banner id="soft-skills-banner" :title="bannerTilteSk" :content="bannerContentSK"></banner>
      <exp></exp>
      <banner id="prog-skills-banner" :title="bannerTitlePS">
        <slot><tab-board :tabTitle="tabTitle"></tab-board></slot>
      </banner>
      <formation></formation>
      <banner id="hard-skills-banner" :title="bannerTilteHS">
        <slot><hard-skills></hard-skills></slot>
      </banner>
      <toolbox></toolbox>
      <slide-show></slide-show>
  </div>

</template>

<script>
import Header from "./components/header.vue"
import Nav from "./components/showNav.vue"
import Banner from "./components/banner.vue"
import Experiences from "./components/experiences.vue"
import Tab from "./components/tab.vue"
import Formation from "./components/formation.vue"
import HardSkills from "./components/hard_skills.vue"
import Toolbox from "./components/toolbox.vue"
import SlideShow from "./components/slideshow.vue"
export default {
  data () {
    return {
      bannerTilteSk: 'Soft Skills',
      bannerContentSK: {
        Curiosité: "Que ce soit dans mon domaine de compétence ou non, j'aime apprendre de nouvelles techniques ou technologie. C\'est d'abord par curiosité puis persevérance que j\'ai appris les techniques de développement web. Aujourd'hui, j'utilise ces compétences acquises de manières autodidacte pour me présenter au travers de cette page internet",
        Initiative: "Au moment de maintenir ou mettre à jour le code des bancs de test sur lesquels j\'ai travaillé, de nouvelles fonctionnalités me sont arrivées en tête. Dans le but d\'améliorer l\'expérience utilisateur, j\'ai pris l'initiative de les développer. Ces initiatives ont été appréciées par les utilisateurs au moment de leur présentation",
        Adaptabilité: "Habitué à travailler dans de petites équipes, et avec du matériels restraint, je suis capable d'adapter mon travail en faveur d\'un objectif. Par exemple, suite au déménagement de nos laboratoires de mesure, la température ambiante n'était plus maitrisé. A la demande d\'un responsable, j\'ai eu à utiliser le matériel immédiatemment disponible pour développer un système de régularisation de température"
      },
      tabTitle: ['C++', 'Python', 'Java'],
      bannerTitlePS: "Prog Skills",
      bannerTilteHS: "Hard Skills",
    }
  },
  components: {
    'app-header': Header,
    'app-nav': Nav,
    'banner': Banner,
    'exp':Experiences,
    'tab-board': Tab,
    'formation': Formation,
    'hard-skills': HardSkills,
    'toolbox': Toolbox,
    'slide-show': SlideShow
  }
}
</script>

<style lang="sass">
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  min-height: 100%

</style>
