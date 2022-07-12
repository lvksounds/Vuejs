<template>
  <div>
    <LayoutTodo />
  </div>
</template>

<script>
import LayoutTodo from "./components/LayoutTodo.vue";

export default {
  name: "App",
  components: {
    LayoutTodo,
  },
};
</script>

<style>
html {
  height: 100%;
  background: #eeeeee;
}
</style>
