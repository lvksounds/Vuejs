<template>
  <div class="m-3">
    <div v-for="task in tasksFilter" :key="task.index">
      <div class="flex flex-row p-2" v-if="!task.deleted">
        <button @click="task.done = !task.done">
          <XIcon class="w-6 text-red-700 flex-none" v-if="task.done" />
          <CheckIcon class="w-6 text-green-600 flex-none" v-else />
        </button>

        <p class="indent-3 grow" :class="{ 'line-through': task.done }">
          {{ task.value }}
        </p>

        <button @click="task.deleted = !task.deleted" v-if="!task.deleted">
          <TrashIcon class="flex-none w-5 justify-self-end" />
        </button>
      </div>
    </div>
  </div>
</template>
<script>
import { CheckIcon, TrashIcon, XIcon } from "@heroicons/vue/solid";

export default {
  name: "TodoList",
  props: {
    newTask: String,
    showFilter: {
      type: String,
      default: "all",
    },
  },
  data() {
    return {
      tasks: [],
      taskIndex: 0,
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
    tasksFilter() {
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
      this.tasks.unshift({
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
