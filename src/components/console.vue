<template>
  <div>
  <!-- <div class="col-sm-12 col-md-7 wrap-console"> -->
    <component :is="consoleName"></component>
  <!-- </div> -->
  <div class="col-sm-12 col-md-2 wrap-button">
    <button type="button" name="button" class="" @click="renderStr">Executer</button>
  </div>

  <div class="col-sm-12 col-md-3 wrap-shell">
    <code>
    <p v-text="langageName"> <p>
    <p>>>></p>
    <p class="renderedString" v-html="strToDisplay"></p></code>
  </div>

  </div>
</template>

<script>
import ConsoleP from './global/console-python.vue'
import ConsoleJ from './global/console-java.vue'
import ConsoleC from './global/console-cpp.vue'
export default {
  props:{
    consoleName:{
      type: String,
      required: true
    },
    langageName:{
      type: String,
      required: true
    }
  },
  data () {
    return {
      strToDisplay:"",
      pieceOfStr: ['<p class="shell-result">Bonjour, je suis  Jérémy Baer j\'ai 28 ans.\
            <br>Je pratique le job de Unicorn seller</p>','<p class="shell-result">Ooops ... !</p>',
            '<p class="shell-result">D\'ingénieur étude et développement</p>', '<br>',
          ],
      currentConsole: this.consoleName,
      langageScore: {"Cpp" : 75, "Python": 80, "Java": 64 }

    }
  },
  watch:{
    langageName: function(){
      this.strToDisplay=""
    }
  },
  methods: {
    renderStr() {
      this.pieceOfStr.push(`<p class="shell-result">Niveau estimé en ${this.langageName} : ${this.langageScore[this.langageName]}</p><br>>>>`)
      this.strToDisplay = this.pieceOfStr.join('')
      this.pieceOfStr.pop()
    }
  },
  components: {
    'console-python': ConsoleP,
    'console-java': ConsoleJ,
    'console-cpp': ConsoleC
  }
}
</script>

<style lang="sass">
@import './../css/console_colors'
@import './../css/console'

</style>
