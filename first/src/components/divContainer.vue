<template>
  <div
    class="container w-3/6 m-auto mt-32 flex flex-col p-10 rounded-sm font-sans space-y-10"
  >
    <loginInputs />

    <simpleButton />

    <loginFooter />
  </div>
</template>

<script>
import loginInputs from "@/components/loginInputs.vue";
import simpleButton from "@/components/simpleButton.vue";
import loginFooter from "@/components/loginFooter.vue";

export default {
  name: "divContainer",
  data() {
    return {};
  },
  components: {
    loginInputs,
    simpleButton,
    loginFooter,
  },
};
</script>

<style></style>
