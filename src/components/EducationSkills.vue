<template>
  <section class="educ-skills">
    <Education />
    <div class="right-side">
      <Skills />
      <Projects />
    </div>
  </section>
</template>

<script>
import Education from "./Education";
import Skills from "./Skills";
import Projects from "./Projects";

export default {
  name: "educ-skills",
  components: {
    Education,
    Skills,
    Projects
  }
};
</script>

<style lang="scss">
.educ-skills {
  display: flex;
  flex-wrap: wrap;
  padding-bottom: 2rem;
}

.right-side {
  display: flex;
  flex-direction: column;
  flex: 30%;
  flex-wrap: wrap;
}

.educ-skills h2 {
  text-transform: uppercase;
}

@media only screen and (max-width: 768px) {
  .educ-skills {
    flex-direction: column;
    flex-wrap: nowrap;
    border-bottom: none;
    padding-bottom: 0;
  }
}
</style>
