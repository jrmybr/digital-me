<template>
  <div >
    <div :class="position"> <!-- Left or right -->
    <div class="content">
      <h2 class="date">{{ date }}</h2>
      <h3> <span class="entreprise">{{ poste.entreprise }}</span> - <span class="poste">{{ poste.poste }}</span></h3>
      <ul class="details-list">
        <li v-for="detail of details">{{detail}}</li>
      </ul>
    </div>
  </div>

  </div>

</template>

<script>

export default {
  props:{
    date:{
      type: String,
      required: true
    },
    poste:{
      type: Object,
      required: true
    },
    details:{
      type: Array,
      required: true
    },
    position:{
      type: String,
      required: true
    }
  },
  data () {
    return {

    }
  },
}
</script>

<style lang="sass">
@import './../../css/couleurs'

.container
    padding: 10px 40px
    position: relative
    background-color: inherit
    width: 50%
    margin-left: 0
.container::after
    content: ''
    position: absolute
    width: 25px
    height: 25px
    right: -12px
    background-color: $white
    border: 4px solid $green
    top: 15px
    border-radius: 50%
    z-index: 1
.left
    left: 0
.right
    left: 50%
.left::before
    content: " "
    height: 0
    position: absolute
    top: 22px
    width: 0
    z-index: 1
    right: 30px
    border: medium solid white
    border-width: 10px 0 10px 10px
    border-color: transparent transparent transparent white
.right::before
    content: " "
    height: 0
    position: absolute
    top: 22px
    width: 0
    z-index: 1
    left: 30px
    border: medium solid white
    border-width: 10px 10px 10px 0
    border-color: transparent white transparent transparent
.right::after
    left: -12px

.content
    padding: 20px 30px
    background-color: $white
    position: relative
    border-radius: 6px
@media all and (max-width: 600px)
  .container
    width: 100%
    padding-left: 50px
    padding-right: 5px
  .container::before
    left: 40px
    border: medium solid $white
    border-width: 10px 10px 10px 0
    border-color: transparent white transparent transparent
  .left::after, .right::after
    left: 15px
  .right
    left: 0%

div.content
  .date
    background-color: $cyan
    font-size: 18px
    text-align: left
  h3
    font-size: 18px
    span.entreprise
      font-size: 16px
    span.poste
      padding:
        left: 10px
        right: 20px
      background-color: $l_violet
  ul
    padding-left: 0
    li
      text-align: justify
      list-style: none
      padding-top: 5px
      line-height: normal
</style>
