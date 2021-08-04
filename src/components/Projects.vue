<template>
  <section class="projects">
    <h2>Projects</h2>

    <div class="projects-list">
      <div v-for="project in projects" :key="project.number" class="project">
        <div class="image-div">
          <img
            class="proj-thumbnail hover-shadow"
            :src="project.data[0].src"
            alt="project image"
            @click="openGallery(0, project.number)"
          />
        </div>
      </div>

      <LightBox ref="lightbox1" :media="IskoIskaData" :show-light-box="false" />
      <LightBox ref="lightbox2" :media="YouShoesData" :show-light-box="false" />
      <LightBox
        ref="lightbox3"
        :media="BalayKalanonData"
        :show-light-box="false"
      />
    </div>
  </section>
</template>

<script>
import Vue from "vue";

// lazy load
import VueLazyLoad from "vue-lazyload";
Vue.use(VueLazyLoad);

// lightbox component
import LightBox from "vue-image-lightbox";
require("vue-image-lightbox/dist/vue-image-lightbox.min.css");

// Project
import IskoIskaData from "../data/IskoIskaData";
import YouShoesData from "../data/YouShoesData";
import BalayKalanonData from "../data/BalayKalanonData";

export default {
  name: "projects",
  components: {
    LightBox
  },
  data() {
    return {
      projects: [
        { data: IskoIskaData, number: 1 },
        { data: YouShoesData, number: 2 },
        { data: BalayKalanonData, number: 3 }
      ],
      IskoIskaData,
      YouShoesData,
      BalayKalanonData
    };
  },

  methods: {
    openGallery(index, ref) {
      if (ref === 1) {
        this.$refs.lightbox1.showImage(index);
      } else if (ref === 2) {
        this.$refs.lightbox2.showImage(index);
      } else {
        this.$refs.lightbox3.showImage(index);
      }
    }
  }
};
</script>

<style lang="scss">
.projects {
  flex-grow: 1;
  padding: 0 2rem;
  /* background-color: #bdf5ee; */
}

.projects-list {
  display: flex;
  justify-content: space-between;
  // gap: 1rem;
}

.projects .project {
  margin-right: 2rem;
}

.project:nth-child(3) {
  margin-right: 0;
}

.project h3 {
  margin-top: 1rem;
  font-weight: 600;
  color: #153330;
}

.project p {
  color: #0c887a;
  font-weight: 500;
}

.image-div {
  flex: 1;
  border-radius: 15px;
}

.projects .image-div:hover {
  /* box-shadow: 0 0 10px white; */
  transition: all 0.3s;
  transform: scale(1.02);
  cursor: pointer;
}
.proj-thumbnail {
  height: 100%;
  width: 100%;
  border-radius: 1rem;
  object-fit: cover;
  overflow: hidden;
}

/* MOBILE VIEW */
@media only screen and (max-width: 768px) {
  .projects {
    padding: 2rem;
    border-bottom: 10px solid #0aaa98;
  }

  .projects .project {
    margin-right: 0;
    margin-bottom: 1rem;
  }
  .project:nth-child(3) {
    margin-bottom: 0;
  }
  .projects h2 {
    margin: 0;
    margin-bottom: 1rem;
  }

  .projects-list {
    flex-direction: column;
    flex-wrap: nowrap;
  }

  .projects h2 {
    text-align: center;
  }

  .image-div {
    height: 80%;
  }

  .proj-thumbnail {
    width: 100%;
  }
}
</style>
