```
<template>
  <section class="education">
    <h2>Education</h2>

    <div class="education-schools" v-for="school in schools" :key="school.name">
      <div class="education-school">
        <img
          class="school-logo"
          :src="require('../assets/schools/' + school.logo)"
          alt="logo here"
        />
        <div>
          <h3>{{ school.name }}</h3>
          <div v-for="item in school.description" :key="item.text">
            <p>{{ item.text }}</p>
            <p>{{ item.year }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
```
<script>
export default {
  name: "education",
  data() {
    return {
      schools: [
        {
          logo: "upvlogo.png",
          name: "University of the Philippines - Visayas",
          description: [
            { text: "B.S. in Computer Science", year: "A.Y. 2018-Present" }
          ]
        },
        {
          logo: "spedlogo.png",
          name: "SPED - Integrated School for Exceptional Children",
          description: [
            { text: "Junior High School Diploma", year: "A.Y. 2015-2016" },
            { text: "Senior High School Diploma", year: "A.Y. 2017-2018" }
          ]
        },
        {
          logo: "nologo.png",
          name: "Jaro 1 Elementary School",
          description: [{ text: "Elementary Diploma", year: "A.Y. 2011-2012" }]
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.education {
  flex: 1;
  display: block;
  padding: 0 2rem;
  /* border-bottom: 10px solid #0aaa98; */
  /* background: #b3e2dd; */
}

.education h2 {
  color: #153330;
}

.education-schools {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.education-school {
  display: flex;
  justify-content: center;
  align-items: center;
}

.education-school > * {
  margin: 1rem;
  color: #153330;
}

.education-school div p {
  font-weight: 500;
  color: #0c887a;
}

.education-school div > * {
  margin: 0.25rem;
}
.school-logo {
  height: 120px;
  width: auto;
}

/* LAPTOP VIEW*/
@media only screen and (max-width: 1024px) {
  .education {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .education-schools {
    justify-content: center;
  }

  .education-school {
    flex-direction: column;
  }

  .education-school div {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .education-school div:last-child {
    margin-bottom: 0.5rem;
  }

  .education-school div h3 {
    text-align: center;
  }

  .school-logo {
    margin-bottom: 0;
  }
}

/* MOBILE VIEW */
@media only screen and (max-width: 768px) {
  .education {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    border-bottom: 10px solid #0aaa98;
  }
}
</style>
