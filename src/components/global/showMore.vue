<template>
  <div class="">
    <div class="wrap-show-more-header">
      <h1 class="title">{{ title }}</h1>
      <div class="subtitle">{{ content }}</div>
    </div>
    <div class="wrap-show-more-details">
      <div class="wrap-details">
        <div class="hide-content"></div>
        <div class="details text-justify">
          <slot></slot>
        </div>
      </div>
      <div @click="displayDetails" class="show-more text-center fa fa-chevron-down down">
        <!-- <span class="fa fa-chevron-down down"></span> -->
      </div>
    </div>
  </div>

</template>

<script>
  export default{
    props:{
      title:{
        type: String,
        required: false
      },
      content:{
        type: String,
        required: false
      }
    },
    data(){
      return {
      }
    },
    methods:{
      displayDetails(event){
        const parent = $(event.target).parent('.wrap-show-more-details')
        parent.find('.wrap-details').toggleClass('show')
        parent.find('.hide-content').toggleClass('show')
        parent.find('.details').toggleClass('show')
        parent.find('.down').toggleClass('fa-chevron-down')
        parent.find('.down').toggleClass('fa-chevron-up')
      }
    }
  }
</script>

<style scoped lang="sass">
@import './../../css/couleurs'

h1.title
  background-color: $cyan
.subtitle
  background-color: $l_violet
.wrap-details
  @media (max-width: 767px)
    max-height: 125px
    &.show
      max-height: none
  .hide-content
    visibility: visible
    min-height: 125px
    background: -moz-linear-gradient(top, rgba(0,0,0,0) 0%, rgba(245,245,245,1) 100%)
    background: -webkit-linear-gradient(top, rgba(0,0,0,0) 0%,rgba(245,245,245,1) 100%)
    background: linear-gradient(to bottom, rgba(0,0,0,0) 0%,rgba(245,245,245,1) 100%)
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#00000000', endColorstr='#a6000000',GradientType=0 )
    @media (min-width: 767px)
      visibility: hidden
    &.show
      visibility: hidden
      min-height: 0
  .details
    position: relative
    margin-top: -125px
    z-index: -1
    max-height: 125px
    overflow: hidden
    @media (min-width: 767px)
      overflow: visible
    &.show
      margin-top: 0
      max-height: none
      overflow: visible
      z-index: 1
.show-more
  background-color: $l_grey
  border-bottom: 1px solid $green
  color: $green
  padding-bottom: 10px
  width: 100%
  @media (min-width: 767px)
    display: none
</style>
