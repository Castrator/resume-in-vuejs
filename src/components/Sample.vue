<template>
  <h1 v-if="sampleProp && sampleProp.length">
    {{ sampleProp }}
  </h1>
</template>
<script>
export default {
  name: "sample",
  props: {
    sampleProp: {
      type: String,
      default: "Yeeee"
    }
  }
};
</script>
<style lang="scss">
ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
