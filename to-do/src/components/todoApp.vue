<template>
  <div
    id="todo-container"
    class="flex flex-col container w-96 h-96 m-auto mt-20 rounded-lg font-ubuntu font-medium shadow-xl"
  >
    <div id="header-container" class="flex flex-row justify-between m-3">
      <div id="titulo" class="flex flex-row">
        <h1 class="text-2xl">
          To <span class="text-indigo-500 font-semibold">Do</span> List
        </h1>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          className="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          strokeWidth="{2}"
        >
          <path
            strokeLinecap="round"
            strokeLinejoin="round"
            d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"
          />
        </svg>
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
        class="border rounded-sm h-10 w-2/3 focus:ring-0 focus:border-0 focus:outline-indigo-500 p-2"
        placeholder="New task"
        v-model="task_text"
      />
      <button
        class="border border-indigo-500 hover:bg-indigo-500 hover:text-indigo-50 w-14 h-10 rounded-sm"
        v-on:click="addTask"
      >
        +
      </button>
    </div>
    <hr />
    <div id="container-newtasks" class="m-3 flex flex-col">
      <div
        id="task"
        class="flex flex-row justify-between border-b border-indigo-500 p-2"
      >
        <p id="task-text">{{ new_task }}</p>
        <div id="task-buttons" class="flex flex-row">
          <CheckIcon class="h-5/6 w-6" id="delBtn" />
          <TrashIcon class="h-5/6 w-5" id="chkBtn" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { CheckIcon } from "@heroicons/vue/solid";
import { TrashIcon } from "@heroicons/vue/solid";

export default {
  name: "todoApp",
  components: { CheckIcon, TrashIcon },
  data() {
    return {
      task_text: "",
      new_task: "",
    };
  },
  methods: {
    addTask() {
      this.new_task = this.task_text;
      let list = document.getElementById("container-newtasks");
      let task = document.getElementById("task");
      let tasktxt = document.getElementById("task-text");
      let taskBtns = document.getElementById("task-buttons");

      list.insertAdjacentElement("beforeend", task);
      task.appendChild(tasktxt);
      task.appendChild(taskBtns);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {
  width: 100%;
}
svg {
  margin-left: 10px;
  width: 25px;
}
</style>
