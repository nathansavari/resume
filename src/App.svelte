<script>
  import resume from "./assets/resume.json"
</script>

<svelte:head>
  <meta property="title" content="Nathan Savari's resume" />
  <meta property="description" content="The resume of a fullstack developer." />
</svelte:head>

<div class="header">
  {resume.basics.name}
  <div class="label">{resume.basics.label}</div>
</div>



<div class="section">
  <div class="section-header">Skills</div>
  {#each resume.skills as skill}
    <div>{skill.name}: {skill.keywords.join(', ')}</div>
  {/each}
</div>

<div class="section">
  <div class="section-header">Work Experience</div>
  {#each resume.work as job}
    <div>
      <b>{job.position} at {job.company}</b>
      <div>{job.startDate} - {job.endDate}</div>
      <div>{job.summary}</div>
    </div>
  {/each}
</div>

<div class="section">
  <div class="section-header">Education</div>
  {#each resume.education as course}
    <div>
      <b>{course.studyType} in {course.area} at {course.institution}</b>
      <div>{course.startDate} - {course.endDate}</div>
      <ul>{#each course.courses as subject}
        <li>{subject}</li>
      {/each}</ul>
      
    </div>
  {/each}
</div>

<style>
  .label {
    font-weight: 400;
    font-size: large;
  }
  .header {
    font-size: 2em;
    font-weight: bold;
  }
  .section {
    margin: 20px 0;
  }
  .section-header {
    margin: 10px 0;
    font-weight: bold;
    font-size: large;
   text-decoration: underline;
  }


</style>