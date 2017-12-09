<template>
  <header id="A%20propos">
    <div class="me col-xs-4" :style="image"></div>
    <show-more class="col-sm-8" :title="title" :content="subtitle | upperCase">
      <slot>
        <p>
        Curieux de nature, je me suis toujours intéressé à la physique.
        Ce qui m'a mené à poursuivre des études dans les mesures physiques. Cette formation
        m'a permis d'apprendre et comprendre plusieurs domaine tel que la thermodynamique, la mécanique,
        la chimie et l'éléctronique dans l'objectif de développer des systèmes de mesures.
        </p>
        <p>
        Ensuite spécialisé dans le domaine de l'électronique et les systèmes de mesures, mes expériences
        professionnelles ont fait de mon profil plus orienté à la partie software. En effet, j'ai eu
        à interfacer plusieurs IHM pour l'intégration d'instrument de mesure.
        </p>
        <p>
        Ayant un goût prononcé pour la programmation, je me suis intéressé puis passionné par le développement
        web et la science des données.
        </p>
      </slot>
    </show-more>
  </header>
</template>

<script>
  import showMore from "./global/showMore.vue"
  export default{
    data(){
      return {
        title: 'Jérémy BAER',
        subtitle: 'Ingénieur étude et développement',
        image: {
          'background': "url('./src/img/me_square.jpg')",
          'background-position': 'center center',
          'background-repeat': 'no-repeat',
          'background-size': 'cover',
        }
      }
    },
    filters:{
      upperCase: (value) => {
        return value.toUpperCase();
      }
    },
    components: {
      'show-more': showMore
    }
  }
</script>

<style scoped lang="sass">

header
  @media (min-width: 767px)
    margin-top: 10%
    min-height: 75%
div.me
  min-height: 330px
  padding-left: 0px
  padding-right: 0px
  @media (max-width: 767px)
    display: none



</style>
