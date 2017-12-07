<template>
  <div class="col-xs-12 banner">
      <div v-if='title' class="title"><h3>{{ title }}</h3></div>
      <div class="wrap-content">
        <slot>
          <div v-for="(key, val) in content"  class="content col-xs-12 col-sm-4">
          <div class="content-title">
            {{ val }}
          </div>
          <div class="content-value text-justify">
            {{ key }}
          </div>
        </div>
      </slot>
      </div>
  </div>

</template>

<script>
export default {
  props:{
    title:{
      type: String,
      required: false
    },
    content: {
      type: Object,
      required: false
    }
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="sass">
@import './../css/couleurs'

div.banner
  display: block
  overflow: auto
  margin-top: 130px
  background: $white
  padding-bottom: 30px
  .title
    text-align: center
    display: block
    overflow: auto
    border-bottom: 2px solid $green
    text-transform: uppercase
  .wrap-content
    .content
      margin-top: 15px
      .content-title
        font-size: 20px
        color: $green
        letter-spacing: -1px
</style>
