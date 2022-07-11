<template>
  <h1>{{ propertyComputed }}</h1>
</template>

<script>
export default {
  name: "LifeCycle",
  data() {
    return {
      property: "Example property",
    };
  },

  computed: {
    propertyComputed() {
      return this.property;
    },
  },

  created() {
    console.log(
      "At this point, this.property is now eactive and property computed will update"
    );
    setTimeout(() => {
      this.property = "example property updated";
    }, 3000);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
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
