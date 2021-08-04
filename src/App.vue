<template>
  <div id="app">
    <Head />
    <Identity />
    <EducationSkills />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import Head from "./components/Header";
import Identity from "./components/Identity";
import EducationSkills from "./components/EducationSkills";
import Contact from "./components/Contact";
import Footer from "./components/Footer";

export default {
  name: "app",
  components: {
    Head,
    Identity,
    EducationSkills,
    Contact,
    Footer
  },
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      secondaryMessage: ""
    };
  },
  methods: {
    changeText() {
      this.secondaryMessage = "Ayoooo noice";
    }
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Ubuntu:ital,wght@0,300;0,400;0,500;0,700;1,300;1,400;1,500;1,700&display=swap");

#app {
  font-family: "Ubuntu", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

p {
  margin: 0px;
}

/* MOBILE VIEW */
@media only screen and (max-width: 768px) {
  body {
    font-size: 0.9em;
  }
}
</style>
