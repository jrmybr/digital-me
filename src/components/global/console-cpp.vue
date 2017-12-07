<template>
  <div>
  <div class="col-sm-12 col-md-7 wrap-console">
    <code>
      <span class="comment">// Powered by Visual Studio Community</span><br><br>

      <span class="comment">// Personne.h</span><br>
      <span class="classe">class</span> Personne
{<br>
<span class="def">public</span>:<br>
	<span class="classe o-tab">Personne</span>(<span class="self">string</span> firstname, <span class="self">string</span> lastname, <span class="def">int</span> age);<br>
	<span class="def o-tab">void</span> addNewSkill(<span class="self">string</span> skillName, <span class="def">int</span> level);<br>
	<span class="def o-tab">void</span> setNewJob(<span class="self">string</span> new_job);<br>
	<span class="self o-tab">string</span> getSkillLevel(<span class="self">string</span> skillName) <span class="def">const</span>;<br>
	<span class="self o-tab">string</span> getJob() <span class="def">const</span>;<br>
	<span class="self o-tab">string</span> presentItsefl() <span class="def">const</span>;<br>

<span class="def">private</span>:<br>
	<span class="self o-tab">string</span> m_firstname;<br>
	<span class="self o-tab">string</span> m_lastname;<br>
	<span class="self o-tab">string</span> m_job;<br>
	<span class="def o-tab">int</span> m_age;<br>
	<span class="self o-tab">map</span>&lt;<span class="self">string</span>, <span class="def">int</span>&gt; m_skills;<br>
};<br>

      <span class="comment">// Personne.cpp</span><br>
      <span class="classe">Personne</span>::Personne(<span class="self">string</span> firstname, <span class="self">string</span> lastname, <span class="def">int</span> age) {<br>
      	<span class="o-tab">m_firstname</span> = firstname;<br>
      	<span class="o-tab">m_lastname</span> = lastname;<br>
      	<span class="o-tab">m_age</span> = age;<br>
      	<span class="o-tab">m_job</span> = <span class="str">"Unicorn seller"</span>;<br>
      };<br>

      <span class="def">void</span> <span class="classe">Personne</span>::addNewSkill(<span class="self">string</span> skillName, <span class="def">int</span> level) {<br>
      	<span class="o-tab">m_skills</span>.insert(pair&lt;<span class="self">string</span>, <span class="def">int</span>&gt;(skillName, level));<br>
      };<br>

      <span class="def">void</span> <span class="classe">Personne</span>::setNewJob(<span class="self">string</span> new_job) {<br>
      	<span class="o-tab">m_job</span> = new_job;<br>
      };<br>

      <span class="self">string</span> <span class="classe">Personne</span>::getSkillLevel(<span class="self">string</span> skillName) <span class="def">const</span> {<br>
      	<span class="return o-tab">return</span> to_string(m_skills.find(skillName)->second);<br>
      };<br>

      <span class="self">string</span> <span class="classe">Personne</span>::getJob() <span class="def">const</span> {<br>
      	<span class="return o-tab">return</span> m_job;<br>
      };<br>

      <span class="self">string</span> <span class="classe">Personne</span>::presentItsefl() <span class="def">const</span> {<br>
      	<span class="o-tab">stringstream</span> ss;<br>
      	<span class="o-tab">ss</span> &lt;&lt; <span class="str">"Bonjour, je suis "</span> &lt;&lt; m_firstname<br>
      		<span class="o-tab">&lt;&lt;</span> <span class="str">" "</span> &lt;&lt; m_lastname &lt;&lt; <span class="str">", j\'ai "</span><br>
      		<span class="o-tab">&lt;&lt;</span> m_age &lt;&lt; <span class="str">" ans.\nje pratique le job de "</span> &lt;&lt;<br>
      		<span class="o-tab">m_job</span>;<br>
      	<span class="return o-tab">return</span> ss.str();<br>
      }<br>
      <span class="comment">// Skills.h</span><br>
      <span class="classe">class</span> Skills
      {<br>
      <span class="def">public</span>:<br>
      	<span class="classe o-tab">Skills</span>(<span class="self">string</span> skillName, <span class="def">int</span> level);<br>
      	<span class="self o-tab">string</span> getSkillName() <span class="def">const</span>;<br>
      	<span class="def o-tab">int</span> getLevel() <span class="def">const</span>;<br>
      	<span class="def o-tab">void</span> setNewLevel(<span class="def">int</span> newLevel);<br>

      <span class="def">private</span>:<br>
      	<span class="self o-tab">string</span> m_skillName;<br>
      	<span class="def o-tab">int</span> m_level;<br>
      };<br>

      <span class="comment">// Skills.cpp</span><br><br>
      <span class="classe">Skills</span>::Skills(<span class="self">string</span> skillName, <span class="def">int</span> level){<br>
      	<span class="o-tab">m_skill</span>Name = skillName;<br>
      	<span class="o-tab">m_level</span> = level;<br>
      };<br>

      <span class="self">string</span> <span class="classe">Skills</span>::getSkillName() <span class="def">const</span> {<br>
      	<span class="return o-tab">return</span> m_skillName;<br>
      };<br>

      <span class="def">int</span> <span class="classe">Skills</span>::getLevel() <span class="def">const</span> {<br>
      	<span class="return o-tab">return</span> m_level;<br>
      }<br>

      <span class="def">void</span> <span class="classe">Skills</span>::setNewLevel(<span class="def">int</span> newLevel) {<br>
      	<span class="o-tab">m_level</span> = newLevel;<br>
      };<br>
      <span class="comment">// Main.cpp</span><br><br>
      #include "Personne.h"<br>
      #include "Skills.h"<br>

      <span class="def">int</span> main()
      {<br>
      	<span class="classe o-tab">Skills</span> jrmy(<span class="str">"Jeremy"</span>,<span class="str">"baer"</span>,28);<br>
      	<span class="classe o-tab">Skills</span>* my_skills[3] = {new <span class="classe">Skills</span>(<span class="str">"Cpp"</span>,75),<br>
      		<span class="o-tab">new</span> <span class="classe">Skills</span>(<span class="str">"Python"</span>,80), new <span class="classe">Skills</span>(<span class="str">"Java"</span>,58) };<br>
      	<span class="def o-tab">for</span> (size_t i = 0; i &lt; 3; i++)
      	{<br>
        <span class="t-tab">jrmy</span>.<span class="functionName">addNewSkill</span>(my_skills[i]-><span class="functionName">getSkillName</span>(),<br>
      <span class="th-tab">my_s</span>kills[i]-><span class="functionName">getLevel</span>());<br>
      	<span class="o-tab">}</span><br>
      	<span class="o-tab">cout</span> &lt;&lt; jrmy.<span class="functionName">presentItsefl</span>() &lt;&lt; endl;<br>
      	<span class="o-tab">cout</span> &lt;&lt; <span class="str">"Ooops... "</span> &lt;&lt; endl;<br>
      	<span class="o-tab">jrmy</span>.<span class="functionName">setNewJob</span>(<span class="str">"Ingenieur etudes et developpement"</span>);<br>
      	<span class="o-tab">cout</span> &lt;&lt; <span class="str">"D\'"</span> &lt;&lt; jrmy.<span class="functionName">getJob</span>() &lt;&lt; <span class="str">"\n"</span> &lt;&lt; endl;<br>
      	<span class="self o-tab">string</span> cppLevel = jrmy.<span class="functionName">getSkillLevel</span>(<span class="str">"Cpp"</span>);<br>
      	<span class="o-tab">cout</span> &lt;&lt; <span class="str">"Niveau estime en C++ : "</span> &lt;&lt; cppLevel &lt;&lt; <span class="str">"%"</span> &lt;&lt; endl;<br>

      	<span class="return o-tab">return</span> 0;<br>
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
      //       '<p class="shell-result">Niveau estimé en C++ : 75%</p>',
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

</style>
