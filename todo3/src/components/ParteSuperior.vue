<template>
  <section>
    <div id="header-container" class="flex flex-row justify-between m-3">
      <div id="titulo" class="flex flex-row">
        <h1 class="text-2xl">
          To <span class="text-indigo-500 font-semibold">Do</span> List
        </h1>
        <BadgeCheckIcon />
      </div>

      <div id="navegacao" class="flex flex-row w-3/6 justify-beetween">
        <a
          href=""
          class="text-xl w-3/6 text-center hover:bg-indigo-500 hover:text-white"
          >All</a
        >
        <a
          href=""
          class="text-xl w-3/6 text-center hover:bg-indigo-500 hover:text-white"
          >Done</a
        >
      </div>
    </div>
    <div id="container-tarefas" class="m-3 flex flex-row justify-between">
      <input
        id=""
        type="text"
        class="border rounded-sm h-10 w-full focus:ring-0 focus:border-0 focus:outline-indigo-500 p-2"
        placeholder="New task"
        v-model="inputText"
      />
      <button
        class="border border-indigo-500 hover:bg-indigo-500 hover:text-indigo-50 w-14 h-10 rounded-sm"
        @click="addTask"
      >
        +
      </button>
    </div>
    <hr />
  </section>
</template>

<script>
import { BadgeCheckIcon } from "@heroicons/vue/outline";

export default {
  name: "ParteSuperior",
  components: { BadgeCheckIcon },
  data() {
    return {
      inputText: "",
    };
  },
  methods: {
    addTask() {
      if (this.inputText) {
        this.$emit("addTask", this.inputText);
        this.inputText = "";
      }
    },
  },
};
</script>
