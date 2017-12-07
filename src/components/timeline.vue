<template>
  <div class="col-xs-12 wrap-timeline">
    <div class="timeline">
      <div class="wrap-timeline-container" v-for="(container,idx) in containers">
        <timeline-container  :position="getPosition(idx)" :date="container.date"
                  :poste="container.poste" :details="container.details"></timeline-container>
      </div>
    </div>
  </div>

</template>

<script>
import TimelineContainer from "./global/timeline-container.vue"
export default {
  props:{
    containers:{
      type: Array,
      required: true
    }
  },
  data () {
    return {
    }
  },
  methods: {
    getPosition: function(idx){
      if (idx%2 == 0){
        return "container left"
      }else{
        return "container right"
      }
    }
  },
  components: {
    'timeline-container': TimelineContainer,
  }
}
</script>

<style lang="sass">
@import './../css/couleurs'
.timeline
  position: relative
  max-width: 1200px
  margin: 0 auto
.timeline::after
  content: ''
  position: absolute
  width: 6px
  background-color: $green
  top: 0
  bottom: 0
  left: 50%
  margin-left: -3px
@media all and (max-width: 600px)
  .timeline::after
    left: 27px
</style>
