<template>
  <div class="flex flex-row justify-center p-2">
    <h1 class="text-2xl">To <span class="text-cyan-500">Do </span>List</h1>
    <ClipboardCheckIcon class="w-8 text-cyan-700 ml-1" />
  </div>

  <div>
    <div class="flex flex-row justify-between p-2 box-border h-14">
      <button
        @click="
          $emit('filter', 'all');
          changeBtn();
        "
        class="bg-cyan-500 text-white w-1/3 m-1 rounded-sm hover:bg-white hover:text-cyan-500 hover:border-cyan-700 hover:border box-border"
      >
        All
      </button>
      <button
        @click="
          $emit('filter', 'done');
          changeBtn();
        "
        class="bg-cyan-500 text-white w-1/3 m-1 rounded-sm hover:bg-white hover:text-cyan-500 hover:border-cyan-700 hover:border"
      >
        Done
      </button>
      <button
        @click="
          $emit('filter', 'undone');
          changeBtn();
        "
        class="bg-cyan-500 text-white w-1/3 m-1 rounded-sm hover:bg-white hover:text-cyan-500 hover:border-cyan-700 hover:border"
      >
        Undone
      </button>
    </div>

    <div class="flex flex-row h-8 justify-around m-1">
      <input
        type="text"
        class="border w-3/4 focus:outline-none focus:border focus:border-cyan-800 indent-2 rounded"
        v-model="text_task"
      />
      <button
        type="button"
        class="text-lg w-16 rounded-sm bg-cyan-500 text-white hover:bg-white hover:text-cyan-500 hover:border-cyan-700 hover:border"
        @click="addTask"
      >
        +
      </button>
    </div>
  </div>
</template>

<script>
import { ClipboardCheckIcon } from "@heroicons/vue/solid";

export default {
  name: "HeaderTodo",
  components: { ClipboardCheckIcon },
  data() {
    return {
      text_task: "",
      btnTrigger: false,
    };
  },
  methods: {
    addTask() {
      if (this.text_task) {
        this.$emit("sendTask", this.text_task);
        this.text_task = "";
      }
    },
    changeBtn() {
      this.btnTrigger = true;
    },
  },
};
</script>
