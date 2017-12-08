<template>
  <nav>
    <div class="col-xs-12 wrap-avatar text-center">
      <div class="c-avatar u-super">
          <img class="c-avatar__img" :src="my_face">
      </div>
    </div>
    <div id="menu" class="col-xs-12 col-md-offset-2 col-md-10">
      <div class="wrap-link col-xs-6 col-md-2 col-lg-2 " v-for="link of links">
        <div class=" text-center">
          <a :href="link">{{ link | upperCase}}</a>
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
        links: ['A propos', 'Expériences', 'Formation',
        'Hard skills','Soft skills', 'Contact']
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
    //display: none
    min-height: 30px
  .wrap-avatar
    padding:
      top: 15px
      bottom: 15px
    background-color: $green
    @media (min-width: 768px)
      display: none

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
