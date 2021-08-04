<template>
  <section class="identity">
    <div class="identity-description">
      <p>
        All-around programmer with emphasis on UI / UX design together with web
        development with the use of HTML5, CSS, and JavaScript. Has an eye for
        good design with the ability to translate artistic touch in his projects
        to improve not only aesthetics but also functionality and practicality.
      </p>
    </div>

    <Artworks />

    <IdentityDetails />
  </section>
</template>

<script>
import Artworks from "./Artworks";
import IdentityDetails from "./IdentityDetails";

export default {
  name: "identity",
  components: {
    Artworks,
    IdentityDetails
  }
};
</script>

<style lang="scss">
.identity-description {
  padding: 2rem;
  font-weight: 500;
  color: white;
  background-color: #246b64;
  display: flex;
  justify-content: center;
}

.identity-description p {
  margin: 0;
}

.identity-details {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  background-color: #153330;
  padding: 2rem;
}

.identity-details span {
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: 500;
}

.identity-details span i {
  margin-right: 0.5rem;
}

.projects-artworks {
  padding: 0 2rem 2rem 2rem;
  background-color: #1d504b;
}

.projects-artworks h2 {
  margin-top: 0;
  padding-top: 1.5rem;
  color: #b8fff7;
}

/* MOBILE VIEW */
@media only screen and (max-width: 768px) {
  .identity-details {
    flex-direction: column;
    gap: 1rem;
  }
}
</style>
