<template>
  <div class="col-xs-12 wrap-slideshow">
    <div class="slideshow-container">

      <div class="mySlides fade" v-for="(slide, idx) in slides">
        <div class="numbertext">{{ idx + 1 }} / 3</div>
        <img :src="slide.img" style="width:100%">
        <div class="text">{{ slide.text }}</div>
      </div>

      <a class="prev" @click="plusSlides(-1)">&lt;</a>
      <a class="next" @click="plusSlides(1)">&gt;</a>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slideIndex: 1,
      slides:[
        {
          img: './src/img/loisirs/crossfit.jpg',
          text: '#CrossFit #Team #Competition'
        },
        {
          img: './src/img/loisirs/dev.jpeg',
          text: '#DevWeb #Create #Digital'
        },
        {
          img: './src/img/loisirs/weightlifting.jpg',
          text: '#Weightlifing #Control #Confident'
        }
      ]
    }
  },
  mounted() {
    //do something after mounting vue instance
    this.showSlides(1)
  },
  methods:{
    plusSlides: function(n){
      console.log(this.slideIndex);
      this.showSlides( this.slideIndex += n)
    },
    showSlides: function(n){
      if (n > 3){ this.slideIndex = 1}
      if (n < 1){ this.slideIndex = 3}
      const slides = $('.mySlides')
      slides.each((idx, element) => {
        $(element).css('display', 'none');
      })
      $(slides[this.slideIndex-1]).css('display', 'block')
    }
  }
}


</script>

<style lang="sass">
@import './../css/couleurs'

.mySlides
  display: none

/* Slideshow container */
.slideshow-container
  //max-width: 1000px
  position: relative
  margin: auto


/* Next & previous buttons */
.prev, .next
  cursor: pointer
  position: absolute
  top: 50%
  width: auto
  padding: 16px
  margin-top: -22px
  color: white
  font-weight: bold
  font-size: 18px
  transition: 0.6s ease
  border-radius: 0 3px 3px 0

/* Position the "next button" to the right */
.next
  right: 0
  border-radius: 3px 0 0 3px

/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover
  background-color: rgba(0,0,0,0.8)

/* Caption text */
.text
  color: #f2f2f2
  font-size: 15px
  padding: 8px 12px
  position: absolute
  bottom: 8px
  width: 100%
  text-align: center

/* Number text (1/3 etc) */
.numbertext
  color: #f2f2f2
  font-size: 12px
  padding: 8px 12px
  position: absolute
  top: 0

/* Fading animation */
.fade
  -webkit-animation-name: fade
  -webkit-animation-duration: 1.5s
  animation-name: fade
  animation-duration: 1.5s

@-webkit-keyframes fade
  from
    opacity: .4
  to
    opacity: 1

@keyframes fade
  from
    opacity: .4
  to
    opacity: 1

@media only screen and (max-width: 300px)
  .prev, .next,.text {font-size: 11px}

</style>
