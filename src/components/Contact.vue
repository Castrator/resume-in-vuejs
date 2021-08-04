<template>
  <section class="contact">
    <center>
      <form>
        <h1 class="hello">{{ text }}</h1>
        <textarea
          class="contact-tarea"
          cols="30"
          row="30"
          placeholder="Enter message here"
        ></textarea
        ><br /><br />
        <button class="contact-btn" type="submit" value="Submit">
          {{ buttonText }}
        </button>
        <br /><br />
      </form>
    </center>
  </section>
</template>

<script>
export default {
  name: "contact",
  data() {
    return {
      text: "What say you?",
      buttonText: "Submit"
    };
  }
};
</script>

<style lang="scss">
.contact * {
  margin: 0;
}

.contact {
  background-image: url("../assets/cover.png");
  color: white;
  padding-bottom: 1rem;
  border-bottom: 10px solid #0aaa98;
}

.contact h1 {
  padding: 1.5rem 0 1rem 0;
}

.contact-tarea {
  height: 12rem;
  background-color: #e2fdfa;
  border: 2px solid #099988;
  border-radius: 15px;
  padding: 1rem;
  font-family: "Ubuntu", sans-serif;
}

.contact-btn {
  border: none;
  padding: 15px;
  font-weight: 600;
  border-radius: 999px;
  color: white;
  background-color: #099988;
}

.contact-btn:hover {
  cursor: pointer;
  background-color: #0bceb7;
  transform: scale(1.1);
  transition: 0.3s;
}

@media only screen and (max-width: 768px) {
  .contact {
    padding: 0 2rem;
  }
  .contact-tarea {
    width: 100%;
  }
}
</style>
