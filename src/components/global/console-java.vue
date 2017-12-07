<template>
  <div>
  <div class="col-sm-12 col-md-7 wrap-console">
    <code>
      <span class="comment">// Powered by : IntelliJ IDEA</span><br><br>
      <span class="comment">// Personne.java</span><br>
      <span class="classe">public class</span> <span class="className">Personne</span> {<br>
        <span class="classe o-tab">private String</span> lastname, firstname, job;<br>
        <span class="classe o-tab">private int</span> age;<br>
        <span class="classe o-tab">private</span> Map&lt;String, Integer&gt; skills;<br>
        <span class="classe o-tab">public</span> <span class="className">Personne</span>(String pLastname, String pFirstname, int pAge){<br>
          <span class="t-tab">lastname</span> = pLastname;<br>
          <span class="t-tab">firstname</span> = pFirstname;<br>
          <span class="t-tab">job</span> = <span class="str">"Unicorn seller"</span>;<br>
          <span class="t-tab">age</span> = pAge;<br>
          <span class="t-tab">skills</span> = new HashMap&lt;&gt;();<br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public void</span> <span class="def">add_new_skill</span>(String skill_name, int level){<br>
          <span class="t-tab">skills.<span class="def">put</span>(skill_name, level);</span><br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public void</span> <span class="def">set_new_job</span>(String new_job){<br>
          <span class="t-tab">job = new_job;</span><br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public String</span> <span class="def">getSkillLevel</span>(String skillName){<br>
          <span class="t-tab return">return</span></span> Integer.<span class="def">toString</span>(skills.get(skillName));<br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public String</span> <span class="def">get_job</span>(){<br>
          <span class="t-tab return">return</span> job;<br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public String</span> <span class="def">toString</span>(){<br>
          <span class="t-tab return">return</span> String.<span class="def">join</span>(<span class="str">" "</span>,<br>
          <span class="str t-tab">"Bonjour, je suis"</span>,<br>
          <span class="t-tab">firstname, lastname,</span><br>
          <span class="str t-tab">", j\'ai"</span>, Integer.<span class="def">toString</span>(age),<br>
          <span class="str t-tab">"ans.\nJe pratique le job de"</span>,<br>
          <span class="t-tab">job);</span><br>
        <span class="o-tab">}</span><br>
      }<br>

      <span class="comment">// Skills.Java</span><br>
      <span class="classe">public class</span> <span class="className">Skills</span> {<br>
        <span class="classe o-tab">private String</span> skillName;<br>
        <span class="classe o-tab">private int</span> level;<br>
        <span class="classe o-tab">private</span> Map&lt;String, Integer&gt; skill = new HashMap&lt;&gt; ();<br>

        <span class="classe o-tab">public</span> <span class="className">Skills</span>(String pSkillName, int pLevel){<br>
          <span class="t-tab">skillName = pSkillName;</span><br>
          <span class="t-tab">level = pLevel;</span><br>
          <span class="t-tab">skill.<span class="def">put</span>(pSkillName,pLevel);</span><br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public String</span> <span class="def">get_skill_name</span>(){<br>
          <span class="t-tab return">return</span> skillName;<br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public int</span> <span class="def">get_level</span>(){<br>
          <span class="t-tab return">return</span> level;<br>
        <span class="o-tab">}</span><br>
        <span class="classe o-tab">public void</span> <span class="def">set_new_level</span>(int new_level){<br>
          <span class="t-tab">level = new_level;</span><br>
        <span class="o-tab">}</span><br>
      }<br>

      <span class="comment">// Main.java</span><br>
      <span class="classe">import</span> com.Personne;<br>
      <span class="classe">import</span> com.Skills;<br>

      <span class="classe">public class</span> <span class="className">Main</span> {<br>

        <span class="classe o-tab">public static void</span> main(String[] args) {<br>
          <span class="t-tab">Personne</span> jrmy = new <span class="className">Personne</span>(<span class="str">"Baer"</span>,<br>
          <span class="str th-tab">"Jérémy"</span>, 28);<br>
          <span class="t-tab">Skills</span> my_skills[] = {new <span class="className">Skills</span>(<span class="str">"cpp"</span>,75),<br>
          <span class="th-tab">new</span> <span class="className">Skills</span>(<span class="str">"Python"</span>,80),<br>
          <span class="th-tab">new</span> <span class="className">Skills</span>(<span class="str">"Java"</span>,64)<br>
        <span class="t-tab">};</span><br>
        <span class="def t-tab">for</span>(int i = 0; i &lt; my_skills.<span class="def">length</span>; i++){<br>
          <span class="th-tab">jrmy</span>.<span class="def">add_new_skill</span>(my_skills[i].<span class="def">get_skill_name</span>(),<br>
          <span class="th-tab">my_skills[i]</span>.<span class="def">get_level</span>());<br>
        <span class="t-tab">};</span><br>
        <span class="t-tab">System</span>.out.<span class="def">println</span>(jrmy.toString());<br>
        <span class="t-tab">System</span>.out.<span class="def">println</span>(<span class="str">"Ooops..."</span>);<br>
        <span class="t-tab">jrmy</span>.<span class="def">set_new_job</span>(<span class="str">"Ingénieur étude et développement"</span>);<br>
        <span class="t-tab">System</span>.out.<span class="def">println</span>(String.join(<span class="str">" "</span>,<br>
        <span class="str th-tab">"D\'"</span>, jrmy.<span class="def">get_job()</span><br>
        <span class="t-tab">};</span><br>
        <span class="t-tab">String</span> javaLevel = jrmy.<span class="def">getSkillLevel</span>(<span class="str">"Java"</span>);<br>
        <span class="t-tab">System</span>.out.<span class="def">println</span>(<span class="str">"Niveau estimé en Java : "</span> + javaLevel + <span class="str">"%"</span>);<br>
      <span class="o-tab">};</span><br>
    }<br>
    </code>

  </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      // strToDisplay: " ",
      // pieceOfStr: ['<p class="shell-result">Bonjour, je suis  Jérémy Baer j\'ai 28 ans.\
      //       <br>Je pratique le job de Unicorn seller</p>','<p class="shell-result">Ooops ... !</p>',
      //       '<p class="shell-result">D\'ingénieur étude et développement</p>','<br>',
      //       '<p class="shell-result">Niveau éstimé en Java : 64%</p>',
      //       '<p class="shell-result">>>></p>'
      //     ]
    }
  },
  methods: {
    renderStr() {
      // this.strToDisplay = this.pieceOfStr.join('')
    },
  }
}
</script>

<style lang="sass">
@import './../../css/console_colors'
@import './../../css/console'

// .wrap-console
//   code
//     font-size: 65%

</style>
