<template>
  <div class="resume__presentations resume__to_space">
    <div class="resume__section_title resume__presentations_title">&sect; {{ title }} </div>
    <div class="resume__content  resume__presentations_container"> 
      <div v-for="(i, idx) in experience" :key="idx">
        <div class="resume__presentation_content">
          <span>{{ i.event }}, {{ i.location }}, {{ i.date }}. </span>

          <span v-for="(m,idx) in i.members" :key="idx">
            <template v-if="idx===0"><b>{{ m }} </b></template>
            <template v-else>{{ m }} </template>
          </span>
          <span>"{{ i.project }}" (poster).</span>
        </div>
        <div class="resume__presentations_works"> 
          Work(s): <a :href="i.link" target="_blank">#1</a>
        </div>
        <template v-if="idx===0"><br/></template>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Presentations',
      experience: [
        {
          event: 'Interprofessional Project Exhibition',
          location: 'Chicago, IL',
          date: 'November 2017',
          members: ['Too, S.','Hoang, P.', 'Stanek, J.','Galasso, G.','Ba, A.'],
          project: 'Innovation in Sports Science & Technology',
          link: '/pdfs/Trackr.pdf'
        },
        {
          event: 'Interprofessional Project Exhibition',
          location: 'Chicago, IL',
          date: 'November 2016',
          members: ['Too, S.','Perez, H.', 'Stanek, J.','Shah, D.'],
          project: 'Innovating Solutions to Urban Problems to Improve Livability (Energy)',
          link: '/pdfs/SolarTurbine.pdf'
        },
      ]
    }
  }
}
</script>

<style>
.resume__presentations_works a {
  text-decoration: underline;
  color: #d4a1fd;
}
</style>