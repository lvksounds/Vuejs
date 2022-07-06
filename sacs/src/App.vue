<template>
  <header-sac msg="header Sac" />
</template>

<script>
import headerSac from "./components/headerSac.vue";

export default {
  name: "App",
  components: {
    headerSac,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
