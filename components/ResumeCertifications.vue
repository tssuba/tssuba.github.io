<template>
  <div class="resume__certifications">

    <div class="resume__to_space" v-for="(i, idx) in certifications" :key="idx">
      <div 
        class="resume__section_title resume__certifications_title"
      > &sect; {{ i.title }} </div>
      <div class="resume__content resume__certifications_container">
        <div class="resume__certifications_content" v-for="(c, idx) in i.content" :key="idx">
          <span>
            {{ c }} ({{ i.year[idx] }})
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      certifications: [
        {
          title: 'Honors and Awards',
          content: [
            'Interprofessional Project Track Award: Innovation in Sports Science & Technology',
             'The M.A. and Lila Self Leadership Academic Scholarship Semi-Finalist',
             'Presidential Scholarship',
             'Tan Sri Dato’ Dr. Jeffrey Cheah Scholarship Award',
             'Treat Every Environment Special (TrEES) Young Voices for Conversation Winner'
             ],
          year: [2017, 2016, '2015-2018', 2013, 2011]
        },
        {
          title: 'Certifications',
          content: [
            'Lean Six Sigma White Belt – US Navy Recruiting Command',
            'Google Analytics Individual Qualification',
            'Advanced Google Analytics',
            'Google Analytics for Beginner'
          ],
          year: [2018, 2018, 2018, 2018]
        },
        {
          title: 'Memberships',
          content: [
            'Association for Computing Machinery',
            'Upsilon Pi Epsilon - Computer Science Honors Society',
          ],
          year: ['2016-2018', 'Awarded in 2018; lifetime membership']
        }
      ]
    }
  }
  
}
</script>