<template>
  <footer class="the-footer">
    <ul class="icons">
      <li class="icon" v-for="icon in icons" :key="icon.link">
        <a :href="icon.link">
          <i :class="icon.icon"></i>
        </a>
      </li>
    </ul>
    <p>© Castrator. All rights reserved.</p>
  </footer>
</template>

<script>
export default {
  name: "the-footer",
  data() {
    return {
      icons: [
        {
          link: "https://www.facebook.com/personalizedfeelings/",
          icon: "fab fa-facebook"
        },
        {
          link: "https://www.instagram.com/personalizedfeelings/",
          icon: "fab fa-instagram"
        },
        {
          link: "https://www.linkedin.com/in/mace-matthew-mirasol-7a93a5214/",
          icon: "fab fa-linkedin-in"
        },
        { link: "https://github.com/Castrator", icon: "fab fa-github" }
      ]
    };
  }
};
</script>

<style lang="scss">
.the-footer {
  padding: 2rem;
  background-color: #153330;
  text-align: center;
  color: white;
}

.icons {
  font-size: xx-large;
  margin-top: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  list-style: none;
  gap: 2rem;
}

.icon a {
  color: #b8fff7;
}

.icon a:hover {
  color: white;
  cursor: pointer;
}
</style>
