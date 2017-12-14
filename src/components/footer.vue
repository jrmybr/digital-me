<template>
  <div id="wrap-footer" class="col-xs-12">
    <div id="footer">
      <div class="footer-column col-sm-4 col-xs-6">
        <div class="header-column text-center">
          Adresse
        </div>
        <div class="content-column">
          <ul>
            <li v-for="part in adresse">{{ part }}</li>
          </ul>
        </div>
      </div>
      <div class="footer-column col-sm-4 col-xs-6">
        <div class="header-column text-center">
          Contact
        </div>
        <div class="content-column">
          <ul>
            <li><span class="fa fa-mobile"> </span> {{ tel }}</li>
            <li><span class="fa fa-envelope"> </span> <a :href="mailto()"> {{ mail }}</a></li>
            <li><span class="fa fa-linkedin-square"> </span> <a href="https://www.linkedin.com/in/j%C3%A9r%C3%A9my-baer-19480786/" target="_blank"> Voir mon profil</a> </li>
          </ul>
        </div>
      </div>
      <div class="footer-column col-sm-4 col-xs-12">
        <div class="header-column text-center">
          Build With
        </div>
        <div class="content-column text-center">
          <ul>
            <li>Web components with Vue.Js </li>
            <li>Selectors with some JQuery</li>
            <li>Basics with HTML 5</li>
            <li>Style with Sass</li>
          </ul>
        </div>
      </div>
      <div class="col-xs-12 created">
        <div class="col-xs-6 text-left">
          Made by <span class="fa fa-heart"></span> and <span class="fa fa-coffee"></span> by Jérémy BAER
        </div>
        <div class="col-xs-6 text-right">
          Updated on 08-12-2017
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import TimelineContainer from "./global/timeline-container.vue"
export default {
  data () {
    return {
      adresse: [
        'BAER Jérémy',
        'Appt B14',
        '7 impasses des pradelets',
        '31650 Saint-Orens-De-Gameville',
      ],
      tel: '06 48 16 64 59',
      mail: 'baer.jeremy@orange.fr'
    }
  },
  methods:{
    mailto: () => {
      return `mailto:${this.mail}`
    }
  }
}
</script>

<style lang="sass">
@import './../css/couleurs'

#wrap-footer
  margin-top: 150px
  min-height: 150px
  background-color: $green
.header-column
  font-size: 16px
  color: $white
.content-column
  color: $l_green
  ul
    padding-left: 0
    li
      list-style: none
      a, :hover
        color: $l_green
.created
  color: darken($green, 10%)
</style>
