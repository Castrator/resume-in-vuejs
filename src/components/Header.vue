<template>
  <header class="the-head">
    <img
      class="image header-image-inside"
      src="../assets/logo2.png"
      alt="profile photo"
    />
    <div class="header-name-title">
      <h1>{{ name }}</h1>
      <div class="header-text">
        <h3>{{ title }}</h3>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "the-header",
  data() {
    return {
      name: "Mace Matthew L. Mirasol",
      title: "Programmer / Illustrator"
    };
  }
};
</script>

<style lang="scss">
.the-head {
  background-image: url("../assets/cover.png");
  background-repeat: no-repeat;
  background-size: cover;
  padding: 1rem;
  color: white;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  border-bottom: 10px solid #0aaa98;
}

.the-head > * {
  margin: 0 1rem;
}

.header-image-inside {
  height: 120px;
  width: auto;
  border-radius: 999px;
  transition: all 0.3s;
}

.header-image-inside:hover {
  box-shadow: 0 0 10px #b8fff7;
  transition: all 0.3s;
  transform: scale(1.1);
  cursor: pointer;
}

.header-name-title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  flex-grow: 1;
}

.header-name-title h1 {
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 48px;
  font-weight: 800;
}

.header-name-title h1,
.header-name-title h3 {
  margin: 0;
}

.header-text {
  list-style-type: none;
  color: #71e2d5;
}

/* MOBILE VIEW */
@media only screen and (max-width: 768px) {
  body {
    font-size: 0.9em;
  }

  .header-text {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .header-name-title h1 {
    text-align: center;
    font-size: 2em;
    margin-top: 1rem;
  }

  .header-text h3 {
    font-size: 1.15em;
  }

  .header-links {
    margin-top: 1rem;
  }
}
</style>
