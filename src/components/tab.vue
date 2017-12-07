<template>
  <div class="col-xs-12 wrap-tab">
    <div class="wrap-title">
    <div class="tab-title" v-for="title of tabTitle">
      <div v-if="title == 'C++'" id="Cpp" @click="updateConsole" class="title active">
        {{ title }}
      </div>
      <div v-if="title != 'C++'" :id="title" @click="updateConsole" class="title">
        {{ title }}
      </div>
    </div>
    </div>
    <div class="col-xs-12 tab-content">
      <!-- <console-java></console-java> -->
      <slot><console-g :consoleName="currentConsole" :langageName="currentLangage"></console-g></slot>
    </div>
  </div>

</template>

<script>
import ConsoleG from './console.vue'
export default {
  props:{
    tabTitle:{
      type: Array,
      required: true
    }
  },

  data () {
    return {
      currentConsole: 'console-cpp',
      currentLangage: 'Cpp'
    }
  },
  components: {
    'console-g': ConsoleG,
  },
  methods:{
    updateConsole(event){
      const clickedElement = event.target
      this.currentConsole = `console-${clickedElement.id.toLowerCase()}`
      this.currentLangage = `${clickedElement.id}`
      $('.tab-title > div.title').each(function(idx,element){
        $(element).removeClass('active')
      })
      $(clickedElement).addClass('active')
    }
  }
}
</script>

<style lang="sass">
@import './../css/couleurs'

.wrap-tab
  margin-top: 15px
  padding:
    left: 0
    right: 0
  .wrap-title
    display: flex
    justify-content: space-around
    border-bottom: 1px solid $green
    min-height: 30px
    text-align: center
    text-transform: uppercase
    .tab-title
      width: 33.333%
      display: grid
      padding: 0
      border-bottom: 1px solid $green
      color: $green
      background-color: $white
      &:nth-child(1n+2)
        border-left: 1px solid green
      .title
        padding-top: 5px
        font-size: 15px
        font-weight: bold
      &:hover
        background-color: $green
        color: $white
        cursor: pointer
      .active
        background-color: $green
        color: $white
  .tab-content
    background-color: $green
    padding:
      top: 15px
      bottom: 15px
</style>
