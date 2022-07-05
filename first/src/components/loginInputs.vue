<template>
  <div class="flex flex-col space-y-10 m-auto">
    <h1 class="text-3xl m-auto font-bold">{{ titleText }}</h1>
    <input
      id="email"
      type="text"
      class="border-b w-96 focus:outline-none focus:border-lime-500"
      placeholder="Username"
    />

    <input
      id="email"
      type="text"
      class="border-b w-96 focus:outline-none focus:border-lime-500"
      placeholder="Password"
    />
  </div>
</template>

<script>
export default {
  name: "loginInputs",
  props: {
    msg: String,
  },
  data() {
    return {
      titleText: "Welcome",
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
