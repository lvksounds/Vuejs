<template>
  <button
    class="bg-lime-600 text-neutral-50 w-80 h-10 m-auto rounded-full hover:bg-lime-800"
  >
    {{ btnLabel }}
  </button>
</template>

<script>
export default {
  name: "simpleButton",
  data() {
    return {
      btnLabel: "Logar",
    };
  },
};
</script>
