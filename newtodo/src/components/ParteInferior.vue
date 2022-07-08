<template>
  <div id="container-newtasks" class="m-3 flex flex-col">
    <div v-for="task in filterTasks" :key="task.index">
      <div
        id="tasks"
        class="flex flex-row justify-between border-b border-indigo-800 p-2"
        v-if="!task.deleted"
      >
        <p id="task-text" :class="{ 'line-through': task.done }">
          {{ task.value }}
        </p>
        <div id="task-buttons" class="flex flex-row">
          <button @click="task.done = !task.done">
            <XIcon class="h-5/6 w-6 text-red-500" v-if="task.done" />
            <CheckIcon class="h-5/6 w-6 text-green-600" id="delBtn" v-else />
          </button>
          <button @click="task.deleted = !task.deleted" v-if="!task.deleted">
            <TrashIcon class="h-5/6 w-5" id="chkBtn" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { CheckIcon, TrashIcon, XIcon } from "@heroicons/vue/solid";
export default {
  name: "ParteInferior",
  props: {
    newTask: String,
    showFilter: {
      type: String,
      default: "all",
    },
  },
  data() {
    return {
      taskIndex: 0,
      tasks: [],
    };
  },
  components: { CheckIcon, TrashIcon, XIcon },

  computed: {
    doneTasks() {
      return this.tasks.filter((task) => task.done);
    },
    undoneTasks() {
      return this.tasks.filter((task) => !task.done);
    },
    filterTasks() {
      if (this.showFilter === "all") {
        return this.tasks;
      } else if (this.showFilter === "done") {
        return this.doneTasks;
      } else {
        return this.undoneTasks;
      }
    },
  },
  watch: {
    newTask(newValue) {
      this.tasks.push({
        index: this.taskIndex,
        value: newValue,
        done: false,
        deleted: false,
      });
      this.taskIndex++;
    },
  },
};
</script>
