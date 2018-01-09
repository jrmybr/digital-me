<template>
  <div class="image-with-desc">
    <img :src="image" :alt="alt_text" class="img-responsive">
    <div class="content">
      <p>{{ desc }}</p>
    </div>
  </div>
</template>

<script>
export default{
  props:{
    image:{
      type: String,
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
img
  margin-top: 10px
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
