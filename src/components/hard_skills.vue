<template>
  <section id="hard-skills" class="col-xs-12">
    <div class="col-sm-4  col-xs-12 text-center" v-for="my_skill in my_hard_skills">
      <p :class="my_skill.icon"></p>
      <p class="hard-skills-desc">{{ my_skill.desc }}</p>
    </div>
  </section>
</template>

<script>
  export default{
    data(){
      return {
        my_hard_skills: [
          {
            icon: "fa fa-cogs g-icon",
            desc: "Analyser une problématique de mesures, déterminer un cahier des charges, séléctionner des composants et des instruments conformes.\
            Je suis capable de proposer une solution technique répondant à un objectif"
          },
          {
            icon: "fa fa-lightbulb-o g-icon",
            desc: "Comprendre de schema électronique, lire une datasheet de composants ou un manuel d\'instrument de mesures.\
            Je suis capable d'intervenir sur la partie hardware d\'un banc de test en toute autonomie"
          },
          {
            icon: "fa fa-code g-icon",
            desc: "Développer un algorithme de commandes, intégrer du matériel sur un banc, valider sa fonctionnalité.\
            Je suis capable de mettre à jour ou maintenir un banc de test en y intégrant de nouveaux moyens technologiques"
          },
          {
            icon: "fa fa-superscript g-icon",
            desc: "Mettre en forme des données, automatiser leur traitement, analyser et interpreter des résultats.\
            Je suis capable d\'utiliser des outils informatiques comme Matlab, Pandas ou MatplotLib pour présenter des résultats "
          },
          {
            icon: "fa fa-file-image-o g-icon",
            desc: "Executer des opérations de filtrage, seuillage ou détecter des objets grâce à des algorithmes de machine learning.\
            Je suis capable de traiter des images à l\'aide d\'outils mathématique et informatique"
          },
          {
            icon: "fa fa-pencil g-icon",
            desc: "Interpreter des résultats, identifier des erreurs de mesures et extraire les informations importantes.\
            Je suis capable un rapport de bilan d\'une campagne d\'essais, tests ou mesures"
          }
        ]
      }
    }
  }
</script>

<style scoped lang="sass">
@import './../css/couleurs'
p.g-icon
  padding-top: 15px
  color: $green
  font-size: 30px
p.hard-skills-desc
  text-align: justify
</style>
