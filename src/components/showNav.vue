<template>
  <nav>
    <div class="col-xs-12 wrap-avatar text-center">
      <div class="u-super">
          <img class="c-avatar" :src="my_face">
      </div>
    </div>
    <div id="menu" class="col-xs-12 col-md-offset-2 col-md-10">
      <div class="wrap-link col-xs-6 col-md-2 col-lg-2 " v-for="link of links">
        <div class=" text-center">
          <a :href="link.link">{{ link.text | upperCase}}</a>
        </div>
      </div>
    </div>
    <div @click="toggleMenu" class="disp-menu col-xs-12 text-center">
      <span class="fa fa-chevron-circle-down down rotation "></span>
    </div>

  </nav>

</template>

<script>
  export default{
    data(){
      return {
        my_face: "./src/img/me_square.jpg",
        links: [{text:'SOFT SKILLS',link:'#soft-skills-banner'},
        {text:'EXPÉRIENCES',link:'#experience-show'},
        {text:'POO SKILLS',link:'#prog-skills-banner'},
        {text:'FORMATIONS',link:'#formation-show'},
        {text:'HARD SKILLS',link:'#hard-skills-banner'},
        {text:'TOOLBOX',link:'#toolbox-show'}
      ]
      }
    },
    filters:{
      upperCase: (value) => {
        return value.toUpperCase();
      }
    },
    methods:{
      toggleMenu(){
        $('#menu').css('display') === "none" ? $('#menu').css('display',"block") : $('#menu').css('display',"none")
        $('span.down').toggleClass('fa-chevron-circle-down')
        $('span.down').toggleClass('fa-chevron-circle-up')
      }
    }
  }
</script>

<style scoped lang="sass">
@import './../css/couleurs'

nav
  min-height: 150px
  background-color: $l_green
  @media (min-width: 768px)
    min-height: 30px
  .wrap-avatar
    padding:
      top: 15px
      bottom: 15px
    background-color: $green
    display: flex
    justify-content: center
    @media (min-width: 768px)
      display: none
    .c-avatar
      max-width: 100px
      border-radius: 50%
      border: 3px solid $white

.disp-menu
  z-index: 999
  min-height: 35px
  background-color: $green
  border-top: 1px solid $l_green
  span
    color: $white
    font-size: 20px
    padding-top: 6px
  @media (min-width: 768px)
    display: none

#menu
  z-index: 999
  padding: 0
  .wrap-link
    display: block
    min-height: 30px
    font-family: 'Squada One', cursive
    padding-top: 3px
    font-size: 18px
    background-color: $l_green
    &:hover
      background-color: $green
      color: $white
    border:
      left: 1px solid $l_grey
      bottom: 1px solid $l_grey
  @media (max-width: 465px)
    display: none

</style>
