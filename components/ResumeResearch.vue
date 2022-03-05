<template>
  <div class="resume__research">
    <div class="resume__section_title resume__research_title">&sect; {{ title }} </div>
    <div class="resume__content resume__research_container"> 
      <div class="resume__to_space" v-for="(i, idx) in experience" :key="idx">
        <div class="resume__research_job_duration">
          <div class="resume__research_job resume__to_bold">
            {{ i.name }}
          </div>
          <div class="resume__research_department">
            , {{ i.department }}
          </div>
          <div class="resume__research_duration resume__to_bold">
            {{ i.duration }}
          </div>
        </div>
        <div class="resume__research_responsibilities">
          <span>Advisor: {{ i.advisor }}</span><br/>
          <span>
            {{ i.responsibilities }}
          </span>
        </div>
        <div class="resume__research_works">
          Work(s): <a :href="i.path" target="_blank">#1</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Research Experience',
      experience: [
        {
          name: 'Illinois Institute of Technology',
          department: 'Interprofessional Project',
          duration: 'Aug - Dec 2017',
          advisor: 'Steve Hammond',
          path: '/pdfs/Trackr.pdf',
          responsibilities: 'Developed project goals and methods. Worked with Division D basketball coach and collected health data from' +
                            'players through simulations and profiled them accordingly. Built hybrid models to provide objective feedback on' +
                            'players’ substitutions through in-game health data. Won the Innovation in Sports Science & Technology Award.'
        },
        {
          name: 'Illinois Institute of Technology',
          department: 'Department of Applied Mathematics',
          duration: 'Aug - Dec 2016',
          advisor: 'Dr. Lulu Kang',
          path: '/pdfs/NeighborhoodSafety.pdf',
          responsibilities: 'Course-based undergraduate research for Probabilities and Statistics. Developed project goals and methods, performed ' +
                            'data cleansing and extraction as well as conducted calculations. Utilized Statistical Hypothesis Testing on data from ' + 
                            'Chicago Data Portal to devise the relationship between crime and locality of university neighborhoods (Grand Boulevard, ' + 
                            'Armor Square, Douglas). Generated heat map based off the results and plotted the crimes accordingly. In collaboration with ' + 
                            'Nelson J. and Turner K.'
        },
        {
          name: 'Illinois Institute of Technology',
          department: 'Interprofessional Project',
          duration: 'Aug - Dec 2016',
          path: '/pdfs/SolarTurbine.pdf',
          advisor: 'Limia Shumia, Bob Anderson',
          responsibilities: 'Developed project goals and methods for “Innovating Solutions to Urban Problems to Improve Livability (Energy)”. ' +
          'The research focused on the possibility of combinatory of renewable energy, in particular solar and wind. Designed presentation poster ' + 
          'and booklet. Collected data from university’s wind turbine and solar panels to calculated the energy generation needed for ROI.'
        },
      ]
    }
  }
}
</script>

<style>
.resume__research_job_duration {
  overflow: hidden;
}

.resume__research_job, .resume__research_department {
  float: left;
}

.resume__research_duration {
  float: right;
}

.resume__research_works a {
  text-decoration: underline;
  color: #d4a1fd;
}
</style>