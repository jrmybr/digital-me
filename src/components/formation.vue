<template>
  <div class="col-xs-12 wrap-experiance">
      <show-more class="col-sm-12" :title="title">
        <slot>
          <timeline :containers="containers"></timeline>
        </slot>
      </show-more>
  </div>

</template>

<script>
import showMore from "./global/showMore.vue"
import Timeline from "./timeline.vue"
export default {
  data () {
    return {
      title: "Formations",
      containers:[
        {
          date: "2013",
          poste:{
            entreprise: 'U Montpellier 2',
            poste: "Master EEA"
          },
          details:['Master Electronique Electrotechnique et Automatique',
            'Mes précédentes formations et ma spécialisation dans le domaine des capteurs et des systèmes associés, je suis capable d\'appréhender une problématique de mesures et y apporter une solution technique',
            'J\'y ai également acquit une capacité de réflexion et de compréhension me permettant de comprendre de nouvelles technologies'
          ]
        },
        {
          date: "2011",
          poste:{
            entreprise: 'IUT Metz',
            poste: "Licence AQI"
          },
          details:['Licence professionnelle Acquisition de Données et Qualification d\'appareillages en milieu industriel',
            'Major de promotion | Mention Bien',
            'Cette formation m\'a permis d\'assoir mes connaissances en acquisition et traitement des données de mesures'
          ]
        },
        {
          date: "2010",
          poste:{
            entreprise: 'IUT Metz',
            poste: "DUT Mesures Physiques"
          },
          details:['Le DUT Mesures Physiques m\'a apporté des connaissances théoriques dans les domaines de la physique-chimie. Connaissances indispensable pour appréhender des systèmes de mesures',
          ]
        },
        {
          date: "2007",
          poste:{
            entreprise: 'Lycée Robert Schuman ',
            poste: "Baccalauréat Scientifique"
          },
          details:['',
          ]
        }
      ]
    }
  },
  components: {
    'show-more': showMore,
    'timeline': Timeline
  }
}
</script>

<style lang="sass">
@import './../css/couleurs'


</style>
