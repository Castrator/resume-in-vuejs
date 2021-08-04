```
<template>
  <section class="projects-artworks">
    <h2>Illustrations</h2>
    <div class="projects-list">
      <div
        v-for="(artwork, index) in ArtworksData"
        :key="artwork.src"
        class="project"
      >
        <div class="image-div">
          <img
            class="proj-thumbnail hover-shadow"
            :src="artwork.thumb"
            alt="project image"
            @click="openGallery(index)"
          />
        </div>
      </div>
    </div>

    <LightBox ref="lightbox0" :media="ArtworksData" :show-light-box="false" />
  </section>
</template>
```
<script>
import Vue from "vue";

// lazy load
import VueLazyLoad from "vue-lazyload";
Vue.use(VueLazyLoad);

// lightbox component
import LightBox from "vue-image-lightbox";
require("vue-image-lightbox/dist/vue-image-lightbox.min.css");

import ArtworksData from "../data/ArtoworksData";

export default {
  name: "projects",
  components: {
    LightBox
  },
  data() {
    return {
      ArtworksData
    };
  },
  methods: {
    openGallery(index) {
      this.$refs.lightbox0.showImage(index);
    }
  }
};
</script>

<style scoped>
.projects-artworks {
  padding: 0 2rem 2rem 2rem;
  background-color: #1d504b;
}

.projects-artworks h2 {
  margin-top: 0;
  padding-top: 1.5rem;
  color: #b8fff7;
  text-transform: uppercase;
}

.projects {
  flex-grow: 1;
  padding: 0 2rem;
}

.projects-list {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
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

.projects-artworks .image-div:hover {
  /* box-shadow: 0 0 10px white; */
  transition: all 0.3s;
  transform: scale(1.02);
  cursor: pointer;
}
.proj-thumbnail {
  height: 100%;
  width: 100%;
  border-radius: 15px;
  object-fit: cover;
  overflow: hidden;
}
</style>
