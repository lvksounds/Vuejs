<template>
  <section>
    <div id="header-container" class="flex flex-row justify-between m-3">
      <div id="titulo" class="flex flex-row">
        <h1 class="text-2xl">
          To <span class="text-indigo-500 font-semibold">Do</span> List
        </h1>
        <BadgeCheckIcon class="w-6 text-indigo-500 ml-2" />
      </div>

      <div id="navegacao" class="grid grid-cols-3 justify-beetween">
        <button
          @click="$emit('filter', 'all')"
          class="text-xl text-center hover:text-indigo-500"
        >
          All
        </button>
        <button
          @click="$emit('filter', 'done')"
          class="text-xl text-center hover:text-indigo-500 mr-4"
        >
          Done
        </button>

        <button
          @click="$emit('filter', 'undone')"
          class="text-xl text-center hover:text-indigo-500"
        >
          Undone
        </button>
      </div>
    </div>
    <div id="container-tarefas" class="m-3 flex flex-row justify-between">
      <input
        type="text"
        class="border rounded-sm h-10 w-full focus:ring-0 focus:border focus:outline-1 focus:outline-indigo-500 p-2"
        placeholder="New task"
        v-model="taskText"
      />
      <button
        class="border border-indigo-500 hover:bg-indigo-500 hover:text-indigo-50 w-14 h-10 rounded-sm"
        @click="sendTask"
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
      taskText: "",
    };
  },
  methods: {
    sendTask() {
      if (this.taskText) {
        this.$emit("addTask", this.taskText);
        this.taskText = "";
      }
    },
  },
};
</script>
