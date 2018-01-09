<template>
  <div class="interest-wrapper">
    <div class="col-xs-12 col-md-4" v-for="image in images">
      <image-with-desc :image="image.dir" :alt_text="image.alt" :desc="image.des"></image-with-desc>
    </div>
    <div class="col-xs-12 col-sm-offset-1 col-sm-10">
      <h3>Outil de visualisation de données</h3>
      <p>Tous les 6 mois, les adhrérents de la salle de CrossFit où
         je m'entraine sont soumis à une série d'entraînement test dans le but d'évaluer les progrés de chacun.
       L'idée de mesurer les progrés des adhérents est bonnes,
       toutefois les résultats sont uniquement présentés sous forme tableur, et oubliés par les adhérents quelques semaines plus tard.</p>
       <p>Pour permettre tout à chacun de retrouver ses anciennes performances, et de les comparer à ses nouvelles, j'ai développé un outil de visualisation de données
        </p>
        <p class="link-to text-center col-xs-12 col-md-offset-3 col-md-6">
        <a href="https://jrmybr.github.io/TestWeeksGalileo/#/" target="blank">Consulter</a></p>
    </div>
  </div>
</template>

<script>
import ImgDesc from './global/img-with-desc.vue'
export default{
  data () {
    return {
      images: [
        {
          dir: './../../src/img/loisirs/crossfit.jpg',
          alt: 'CrossFit',
          des: 'Passionné par le CrossFit depuis plus de 3 ans, si je le pratique\
          surtout en tant que loisir, je participe régulièrement à des compétitions\
          individuelles ou en équipes'
        },
        {
          dir: './../../src/img/loisirs/weightlifting.jpg',
          alt: 'Halterophilie',
          des: 'L\'haltérophilie est une composante du CrossFit, c\'est ainsi que \
          j\'ai débuté sa pratique. C\'est un discipline qui recquiere de la confiance \
          en soi, de la rigueur et de la technique. Mes performances me permettent \
          de concourir dans la catégorie inter-regionale'
        },
        {
          dir: './../src/img/loisirs/dev.jpeg',
          alt: 'Dev. Web',
          des: 'Je me suis intéressé au développement web dans le but de coder une application\
          en rapport avec ma pratique sportive. Depuis que j\'ai posé un pied dans cet univers\
          digital, je m\'investi dans l\'apprentissage de nouveaux outils.'
        },
      ]
    }
  },
  components: {
    'image-with-desc': ImgDesc
  }
}
</script>

<style scoped lang="sass">
@import './../css/couleurs'
.interest-wrapper
  margin-top: 30px
  text-align: justify
p.link-to
  min-height: 40px
  padding-top: 3px
  font-size: 24px
  letter-spacing: -1px
  text-transform: uppercase
  border: 2px solid $green
  a
    color: $green
    &:hover
      text-decoration: none
  &:hover
    background-color: $green
    border: 2px solid $white
    a
      color: $white
</style>
