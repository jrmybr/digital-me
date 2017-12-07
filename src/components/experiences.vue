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
      title: "Expériences",
      containers:[
        {
          date: "Oct. 2013 - Jan. 2017",
          poste:{
            entreprise: 'ISAE-SUPAERO',
            poste: "Ingénieur R&D"
          },
          details:['Maintenir le script C++ codant les bancs de mesures',
            'Faire évoluer l\'ensemble des bancs avec de nouvelles fonctionnalités',
            'Mettre au point un protocole de mesures pour images en couleur',
            'Développer de nouveaux scripts de traitement de données sous Matlab'
          ]
        },
        {
          date: "Fév. 2013 - Aoû. 2013",
          poste:{
            entreprise: 'CNES',
            poste: "Ingénieur R&T (stage)"
          },
          details:['Développer, avec LabView, un banc de caractérisation de capteurs d\'images CMOS',
            'Développer de nouveaux scripts de traitement de données sous Scilab',
            'Utiliser les outils développés pour caractériser les performances électro-optique d\'un capteur',
          ]
        },
        {
          date: "Fév. 2011 - Aoû. 2011",
          poste:{
            entreprise: 'CERAH',
            poste: "Technicien supérieur d'études (stage)"
          },
          details:['Développer, avec LabView, un banc de test de fatigue des systèmes de freinage de fauteuil roulants',
            'Assurer l\'étalonnage des capteurs équipants le banc de test',
            'Développer un régulateur de position en utilisant la logique floue',
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
