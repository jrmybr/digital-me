<template>
  <div id="app">
      <app-nav></app-nav>
      <app-header></app-header>
      <banner id="soft-skills-banner" :title="bannerTilteSk" :content="bannerContentSK"></banner>
      <exp id="experience-show"></exp>
      <banner id="prog-skills-banner" :title="bannerTitlePS">
        <slot><tab-board :tabTitle="tabTitle"></tab-board></slot>
      </banner>
      <formation id="formation-show"></formation>
      <banner id="hard-skills-banner" :title="bannerTilteHS">
        <slot><hard-skills></hard-skills></slot>
      </banner>
      <toolbox id="toolbox-show"></toolbox>
      <banner id="interest-banner" :title='bannerTitleInt'>
        <slot><interest></interest></slot>
      </banner>
      <app-footer id="contact"></app-footer>
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
import Interest from "./components/interest.vue"
import Footer from "./components/footer.vue"

export default {
  data () {
    return {
      bannerTilteSk: 'Soft Skills',
      bannerContentSK: {
        Curiosité: "Que ce soit dans mon domaine de compétence ou non, j'aime apprendre de nouvelles techniques ou technologies.\
         C\'est d'abord par curiosité, puis persevérance, que j\'ai appris les techniques de développement web Back et Front end. \
         Aujourd'hui, j'utilise ces compétences acquises de manières autodidacte pour me présenter au travers de cette page internet",

        Initiative: "Je n\'ai pas peur de prendre des initiatives si je suis convaincu qu\'elles peuvent être bénéfique au projet.\
        J\'ai souvent mis en oeuvre cette philosophie pour ajouter de nouvelles fonctionnalités sur les bancs sur lesquels j'ai travaillé. \
        Toujours dans le but d\'améliorer l\'expérience utilisateur, mes initiatives ont toujours été apprécié des utilisateurs",

        Adaptabilité: "Habitué à travailler dans de petites équipes, et avec du matériel limité, je suis capable d'adapter \
         mon travail en faveur d\'un objectif. Par exemple, suite au déménagement de nos laboratoires de mesure,\
          la température ambiante n'étant plus maitrisé, j\'ai eu à utiliser le matériel \
          immédiatemment disponible pour développer un système de régularisation de température"
      },
      tabTitle: ['C++', 'Python', 'Java'],
      bannerTitlePS: "Prog Skills",
      bannerTilteHS: "Hard Skills",
      bannerTitleInt: "Centre d\'intérêt"
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
    'interest': Interest,
    'app-footer': Footer
  }
}
</script>

<style lang="sass">
@import './src/css/couleurs'
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  min-height: 100%
#contact
  background-color: $green
  margin-top: 50px
  @media (min-width: 600px)
    margin-top: 150px
</style>
