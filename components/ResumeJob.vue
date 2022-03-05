<template>
  <div class="resume__experience">
    <div class="resume__section_title resume__experience_title"> &sect; {{ title }} </div>
    <div class="resume__content resume__experience_container"> 
      <div class="resume__to_space" v-for="i in experience" :key="i.name">
        <div class="resume__experience_job_duration">
          <div class="resume__experience_job resume__to_bold">
            {{ i.name }}
          </div>
          <div class="resume__experience_location">
            , {{ i.institution }}, {{ i.location }}
          </div>
          <div class="resume__experience_duration resume__to_bold">
            {{ i.duration }}
          </div>
        </div>
        <ul class="resume__experience_responsibilities">
          <li v-for="(r, idx) in i.responsibilities" :key="idx">
            {{ r }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Working Experience',
      experience: [
        /*{
          name: 'Data Scientist',
          institution: 'Reply LLC',
          location: 'Chicago',
          duration: 'Jun 2018 - Dec 2020',
          responsibilities: [
            'Posted onsite with a company produces agricultural, construction, and commercial equipment from end-to-end (chassis and engine design, development, production).',
            'Implemented and enforced software methodologies throughout digital analytics product development phases. Set up checkpoints to uphold process integrity with product owner.',
            'Built and productionized ETL pipelines with Data Lake, Data Factory, and Databricks from Microsoft Azure platform. Revised underlying data structure using PySpark and reduced data lookup from O(N) to O(1).',
            'Spearheaded in-house digital analytics product. Built end-to-end (UI/UX, API etc.) reactive control room using Vue.js, D3.js, Flask, Celery, Redis and Data Lake. Integrated Auth0 for access regulation.',
            'Refactored legacy data analysis use-cases and migrated from local to cloud. Automated report generation and update into Microsoft Power BI.'
          ]
        },*/
        {
          name: 'Systems Specialist',
          institution: 'Library of Health Sciences, University of Illinois at Chicago',
          location: 'Chicago',
          duration: 'Fall 2021 - Present',
          /*responsibilities: [
            'Tutored on concepts of virtual memory, UNIX, shell and more.',
            'Hosted in-person tutoring as well as via emails and online forum.',
            'Served in the same position for 4 consecutive semesters. (2 academic years)',
            'Total students tutored over 200+.'
          ]*/
        },
        {
          name: 'Undergraduate Teaching Assistant',
          institution: 'University of Illinois at Chicago',
          location: 'Chicago',
          duration: 'Summer 2020 - Spring 2021',
          /*responsibilities: [
            'Tutored on concepts of virtual memory, UNIX, shell and more.',
            'Hosted in-person tutoring as well as via emails and online forum.',
            'Served in the same position for 4 consecutive semesters. (2 academic years)',
            'Total students tutored over 200+.'
          ]*/
        },
        /*{
          name: 'Technology Consulting Summer Analyst',
          institution: 'Accenture PLC',
          location: 'Kuala Lumpur',
          duration: 'May - Aug 2017',
          responsibilities: [
            'Posted on site to work with the largest power company in Southeast Asia on an ITSM project.',
            'Integrated multiple monitoring tools (Dynatrace, ManageEngine, Aruba, HP IMC, Zscaler and more) as well as CMDB Remedy onto Splunk -- displaying different network and application metrics.',
            'Wrote Python scripts to eliminate manual data extraction and entry for hardware devices\' information from client\'s internal device management tool.',
            'Successfully developed and tested monitoring tool dashboard to reflect the health statuses of the monitoring tools.',
            'Spearheaded and streamlined the process flow of data visualizations through Splunk\'s Search Processing Language into automation; allowing end users to be less technical.',
            'Received return offer.'
          ]
        },
        {
          name: 'Software Engineering Intern',
          institution: 'Freescale Semiconductors Inc. (acquired by NXP Semiconductors)',
          location: 'Kuala Lumpur',
          duration: 'April - July 2015',
          responsibilities: [
            'Maintained and enhanced the in-house manufacturing software.',
            'Added barcode scanning functionality for operators to use in production lines and saved approx. 10 minutes per scan producing each chip.',
            'Handled multiple change requests and pushed the work to production environment.',
            'Spearheaded the internal web (intranet) migration project using Microsoft Sharepoint.'
          ]
        },*/
      ]
    }
  }
}
</script>

<style>
.resume__experience_job_duration {
  overflow: hidden;
}

.resume__experience_job, .resume__experience_location {
  float: left;
}

.resume__experience_duration {
  float: right;
}

.resume__experience_job {
  color: #c37aff;
  /* color: #744ce4; */
}

.resume__experience_background {
  margin-bottom: 5vh;
}
</style>
