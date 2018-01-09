<template>
  <div :style="image" class="image-with-desc">
    <div class="content">
      <p>{{ desc }}</p>
    </div>
  </div>
</template>

<script>
export default{
  props:{
    image:{
      type: Object,
      required: true
    },
    alt_text:{
      type: String,
      required: true
    },
    desc:{
      type: String,
      required: true
    }
  },
}
</script>

<style scoped lang="sass">
.image-with-desc
  margin-top: 10px
  min-height: 300px
.content
  position: absolute
  bottom: 0
  background: rgba(0, 0, 0, 0.5)
  color: #f5f5f5
  font-size: 11px
  border-radius: 0
  width: 93%
  min-height: 80px
  max-height: 80px
  @media (max-width: 600px)
    width: 90%

</style>
