@media print {
    .pagebreak {
        clear: both;
        page-break-after: always;
    }
}

<template>
  <div class="resume">
    <!-- <PageTitle/> -->
    <div class="resume__container" id="resume__container">
      <div class="resume__info">
        <div class="resume__lastUpdate">
          Last updated: March 4, 2022
        </div>
        <div class="resume__download">
          <span>download: </span>
          <a href="/pdfs/tanmaysubaresume2022.pdf" target="_blank">resume</a>
          <!-- <a href="/pdfs/tanmaysubaresume2022.pdf" target="_blank">curriculum vitae</a> -->
        </div>
      </div>
      <p style="page-break-after: always;">&nbsp;</p>
      <p style="page-break-before: always;">&nbsp;</p>
      <ResumeHeader/>
      <ResumeDivider/>
      <ResumeEducation/>
      <ResumeJob/>
      <!--<ResumeResearch/>
      <ResumePresentations/>
      <ResumeCertifications/>-->
      <ResumeTechnicalSkills/>
      <ResumeLanguage/>
    </div>
  </div>
</template>

<style scoped>
.resume__container {
  background-color: #201e1e;
}

.resume__container * {
  color: white;
}

.resume__info {
  margin-top: 5vh;
  padding-bottom: 5vh;
}

.resume__lastUpdate {
  float: left;
}

.resume__download {
  margin: auto;
  text-align: right;
  float: right;
}

.resume__download a {
  text-decoration: none;
  border-bottom: solid .5px white;
}

.resume__download a:hover {
  color: #00c58e;
}

.resume__container {
  width: 90%;
  margin: auto;
  border: 1.5px solid white;
  margin-top: 10vh;
  padding-left: 2vw;
  padding-right: 2vw;
}

.resume__container * {
  font-family: 'proxima-nova', serif;
}

@media only screen and (max-width: 640px) {
  .resume__container {
    height: 80%;
    margin-bottom: 35%;
  }
  .resume__container * {
    font-size: .75em;
  }
}
</style>
