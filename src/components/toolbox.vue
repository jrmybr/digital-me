<template>
  <section id="my-tools-box" class="col-xs-12">
    <show-more class="col-sm-12" :title="title">
      <slot>
        <div class="wrap-toolbox">
          <div class="group" v-for="(group, groupName) in groups">
            <div class="groupname">{{ groupName }}</div>
            <div class="tools">
              <div  class="tool" v-for="item in group">
                <span class="name">{{ item.name }}</span>
                <span class="stars" v-html="getStars(item.stars)"></span>
              </div>
            </div>
          </div>
          </div>
      </slot>
    </show-more>
  </section>
</template>

<script>
import showMore from "./global/showMore.vue"
  export default{
    data(){
      return {
        title: "Toolbox",
        groups:{
          'POO': [{name:'C++',stars:4}, {name:'Java',stars:3}, {name:'Python 3',stars:4}],
          'NI': [{name:'LabView',stars:4}, {name:'LabWindows',stars:3}, {name:'Teststand',stars:2}],
          'Scientifique': [{name:'Matlab',stars:4}, {name:'Numpy',stars:3}, {name:'Pandas',stars:4}, {name:'MatplotLib',stars:3}],
          'Web back-end': [{name:'Django',stars:3}, {name:'PostgreSQL',stars:3}, {name:'Firebase',stars:3}],
          'Web Front-end': [{name:'HTML5/CSS3',stars:4},{name:'JavaScript',stars:4},{name:'Vue.js',stars:4}, {name:'ReactJs',stars:3}],
          'En vrac': [{name:'Git',stars:3},{name:'Linux',stars:3}, {name:'D3.js',stars:3}, {name:'Trello',stars:4}]
        }
      }
    },
    methods:{
      getStars: (stars) =>{
        let html = []
        for(let i=0; i<5; i++){
          if (i < stars){
            html.push('<span class="fa fa-star filled" style="color: #239b56;"></span>')
          }else{
            html.push('<span class="fa fa-star"></span>')
          }
        }
        return html.join('')
      }
    },
    components: {
      'show-more': showMore
    }
  }
</script>

<style scoped lang="sass">
@import './../css/couleurs'
.wrap-toolbox
  display: flex
  justify-content: space-around
  flex-wrap: wrap
  .group
    width: 100%
    @media (min-width: 600px)
      width: 33.333%
    .groupname
      background-color: #ce93d8
      margin-right: 20px
      padding-left: 15px
      font-weight: bold
    .tools
      .tool
        display: flex
        .name
          width: 33.3%
        .stars
          width: 66.6%
          color: $l_green
</style>
