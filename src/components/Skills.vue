<template>
  <section class="skills">
    <h2>SKILLS</h2>

    <div class="actual-skills">
      <badger-accordion
        class="skill-tree"
        v-for="skill in skills"
        :key="skill.name"
      >
        <badger-accordion-item>
          <div slot="header" class="collapsible">{{ skill.name }}</div>
          <div
            slot="content"
            class="skiller"
            v-for="sk in skill.skill"
            :key="sk.name"
          >
            <p class="skill">
              <img
                class="skill-icon"
                :src="require('../assets/skills/' + sk.logo)"
              />
              <!-- {{ sk.name }} -->
            </p>
          </div>
        </badger-accordion-item>
      </badger-accordion>
    </div>
  </section>
</template>

<script>
import { BadgerAccordion, BadgerAccordionItem } from "vue-badger-accordion";
import { CPlusPlusIcon } from "vue-simple-icons";

export default {
  name: "skills",
  components: {
    BadgerAccordion,
    BadgerAccordionItem,
    CPlusPlusIcon
  },
  data() {
    return {
      skills: [
        {
          name: "Programming",
          skill: [
            { name: "C", logo: "c.svg" },
            { name: "C++", logo: "cplusplus.svg" },
            { name: "Java", logo: "java.svg" },
            { name: "Python", logo: "python.svg" }
          ]
        },
        {
          name: "Web Development",
          skill: [
            { name: "CSS", logo: "css3.svg" },
            { name: "PHP", logo: "php.svg" },
            { name: "HTML", logo: "html5.svg" },
            { name: "JavaScript", logo: "javascript.svg" }
          ]
        },
        {
          name: "Software",
          skill: [
            { name: "Illustrator", logo: "adobeillustrator.svg" },
            { name: "Photoshop", logo: "adobephotoshop.svg" },
            { name: "MS:Office", logo: "microsoftoffice.svg" },
            { name: "Google Suite", logo: "google.svg" }
          ]
        }
      ]
    };
  }
};
</script>

<style>
.skills {
  padding: 0 2rem;
}
.actual-skills {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 2rem;
  transition: all 0.5s ease-in-out;
}
.skill-tree {
  display: flex;
  flex-direction: column;
  flex: 1;
  gap: 1rem;
  flex-wrap: wrap;
  margin: 0;
}
.skill-icon {
  height: 1.5rem;
  color: white;
  width: auto;
  /* margin-right: 0.4rem; */
}
.badger-accordion__header {
  font-family: "Ubuntu", sans-serif;
  width: 100%;
  padding: 1.2rem;
  border: none;
  outline: none;
  cursor: pointer;
  background: #153330;
  border-radius: 999px;
  text-align: left;
  transition: background 0.2s;
}

.badger-accordion-toggle {
  font-family: "Ubuntu", sans-serif;
  color: white;
  font-size: 1rem;
  font-weight: 500;
}

.badger-accordion__panel {
  margin: 0;
}

.js-badger-accordion-panel-inner {
  display: flex;
  /* flex-direction: column; */
  justify-content: center;
  gap: 1rem;
}

.skiller {
  display: flex;
  flex-wrap: wrap;
  margin: 0;
  padding: 0;
  gap: 1.2rem;
  overflow: hidden;
  justify-content: center;
  transition: max-height 0.2s ease-in-out;
}

.skill {
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 500;
  border-radius: 999px;
  background-color: #1b504b;
  transition: all 0.5s ease-in-out;
  flex: 1;
  text-align: center;
}

.skiller:last-child .skill {
  font-size: 0.8em;
}

.skill-tree p {
  border-radius: 999px;
  background-color: #1b504b;
  color: white;
  padding: 1rem;
}

.badger-toggle-indicator {
  font-size: 1.2rem;
}

/* LAPTOP VIEW*/
@media only screen and (max-width: 1024px) {
  .actual-skills {
    flex-direction: column;
  }
}
/* MOBILE VIEW */
@media only screen and (max-width: 768px) {
  .skills {
    text-align: center;
    border-bottom: 10px solid #0aaa98;
  }
  .actual-skills {
    display: block;
  }

  .skill-tree + .skill-tree {
    margin-top: 1rem;
  }

  .skill-tree:last-child {
    margin-bottom: 1rem;
  }

  .skiller {
    margin: 0;
  }
}
</style>
