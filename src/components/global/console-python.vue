<template>
  <div>
  <div class="col-sm-12 col-md-7 wrap-console">
    <code>
      <span class="comment"># Powered by : PyCharm</span><br><br>
      <span class="classe">class</span> <span class="className">Personne</span>():<br>
      <span class="def o-tab">def</span> <span class="functionName">__init__</span>(<span class="self">self</span>,firstname,lastname,age,job=<span class="str">"Unicorn seller"</span>):<br>
      <span class="self t-tab">self</span>._firstname=firstname<br>
      <span class="self t-tab">self</span>._lastname=lastname<br>
      <span class="self t-tab">self</span>._job=job<br>
      <span class="self t-tab">self</span>._age=age<br>
      <span class="self t-tab">self</span>._skills={}<br>

      <span class="def o-tab">def</span> <span class="functionName">set_new_job</span>(<span class="self">self</span>,new_job):<br>
      <span class="self t-tab">self</span>._job = new_job<br>

      <span class="def o-tab">def</span> <span class="functionName">add_new_skill</span>(<span class="self">self</span>,skill):<br>
      <span class="self t-tab">self</span>._skills.<span class="functionName">update</span>(skill)<br>

      <span class="def o-tab">def</span> <span class="functionName">get_skills</span>(<span class="self">self</span>):<br>
      <span class="return t-tab">return</span> <span class="self">self</span>._skills<br>

      <span class="def o-tab">def</span> <span class="functionName">__str__</span>(<span class="self">self</span>):<br>
      <span class="return t-tab">return</span> " ".<span class="functionName">join</span>(( <span class="str">"Bonjour, je suis "</span>,<br>
      <span class="t-tab">self._firstname, self._lastname,<br></span>
      <span class="t-tab"><span class="str">"j\'ai"</span>, str(self._age),<br></span>
      <span class="t-tab"><span class="str">"ans.\nJe pratique le job de"</span>,  self._job))<br>

      <span class="classe">class</span> <span class="className">Skill</span>():<br>
      <span class="def o-tab">def</span> <span class="functionName">__init__</span>(<span class="self">self</span>, skill_name, level=0):<br>
      <span class="self t-tab">self</span>._skill_name= skill_name<br>
      <span class="self t-tab">self</span>._level= level<br>

      <span class="def o-tab">def</span> <span class="functionName">get_skill_name</span>(<span class="self">self</span></span>):<br>
      <span class="return t-tab">return</span> <span class="self">self</span>._skill_name<br>

      <span class="def o-tab">def</span> <span class="functionName">set_new_level</span>(<span class="self">self</span>,new_level):<br>
      <span class="self t-tab">self</span>._level = new_level<br>

      <span class="def o-tab">def</span> <span class="functionName">get_skill</span>(<span class="self">self</span>):<br>
      <span class="return t-tab">return</span> {<span class="self">self</span>._skill_name: <span class="self">self</span>._level}<br>
      <br>if __name__ == <span class="str">'__main__'</span>:<br>
      <span class="o-tab">jrmy</span> = Personne(<span class="str">'Jérémy'</span>, <span class="str">'Baer'</span>, 28)<br>
      <span class="o-tab">my_skills</span>= [Skill(<span class="str">'cpp'</span>,75),<br>
      <span class="o-tab">Skill</span>(<span class="str">'Python'</span>,80),Skill(<span class="str">'Java'</span>,64)]<br>
      <span class="functionName o-tab">for</span> my_skill <span class="functionName">in</span> my_skills:<br>
      <span class="t-tab"> jrmy</span>.<span class="functionName">add_new_skill</span>(my_skill.<span class="functionName">get_skill()</span>)<br>

      <span class="functionName o-tab">print</span>(jrmy.<span class="functionName">__str__()</span>)<br></span>

      <span class="functionName o-tab">print</span>(<span class="str">"Ooops ..."</span>)<br>

      <span class="o-tab">jrmy</span>.<span class="functionName">set_new_job</span>(<span class="str">'Ingénieur étude et développement'</span>)<br>
      <span class="functionName o-tab">print</span>(<span class="str">" "</span>.<span class="functionName">join</span>((<span class="str">'D'</span>, jrmy.job)))<br>

      <span class="o-tab">python_level</span> = jrmy.<span class="functionName">get_skills()</span>[<span class="str">'Python'</span>]<br>
      <span class="functionName o-tab">print</span>(<span class="str">'Niveau estimé en Python : {0}'</span>.format(python_level))<br>
    </code>

  </div>


  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  methods: {
  }
}
</script>

<style lang="sass">
@import './../../css/console_colors'
@import './../../css/console'

</style>
