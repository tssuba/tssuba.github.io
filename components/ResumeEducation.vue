<template>
  <div class="resume__education">
    <div class="resume__section_title">&sect; {{ title }}</div>
    
    <div class="resume__content resume__education_container">
      <div class="resume__to_space" v-for="i in education" :key="i.name">
        <div class="resume__education_school_class">
          <div class="resume__education_school resume__to_bold">
            {{ i.name }}
          </div>
          <div class="resume__education_location">
            , {{ i.city }}, {{ i.state }}, {{ i.country }}
          </div>
          <div class="resume__education_class resume__to_bold">{{ i.class }}</div>
        </div>
        <div class="resume__education_degree">
          {{ i.degree }}
        </div>
        <div class="resume__education_coursework" v-if="i.coursework">
          <em>Relevant Coursework: </em>
          <template v-for="c in i.coursework">
            {{ c }}
          </template>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Education',
      education: [
        {
          name: 'University of Illinois at Chicago',
          city: 'Chicago',
          state: 'IL',
          country: 'United States',
          class: '2023',
          degree: 'Bachelor of Science in Computer Science',
          /*gpa: '3.67',
          honor: 'cum laude',
          coursework: [
            'Geospatial Vision & Visualization,', 
            'Advanced Data Mining,', 
            'Operating Systems,',
            'Online Social Network Analysis,', 
            'Discrete Mathematics'
          ]*/
        },
        /*{
          name: 'Sunway University',
          city: 'Petaling Jaya',
          state: 'Selangor',
          country: 'Malaysia',
          class: '2015',
          degree: 'American Degree Transfer Program',
          gpa: '3.86',
          honor: 'magna cum laude',
          coursework: ''
        }*/
      ]
    }
  }
}
</script>

<style>
/* generic for resume */
.resume__section_title {
  font-size: 1.2em;
  font-weight: bold;
  text-transform: uppercase;
  margin-bottom: 1vh;
  color: #00c58e;
}

.resume__content {
  font-size: 1.1em;
}

.resume__to_bold {
  font-weight: bold;
}

.resume__to_italicize {
  font-style: italic;
}

.resume__to_space {
  margin-bottom: 5vh;
}

/* education component */
.resume__education_school_class {
  overflow: hidden;
}


.resume__education_school, .resume__education_location {
  float: left;
}
.resume__education_class {
  float: right;
}

.resume__education_coursework {
  margin-top: 3vh;
}

</style>
