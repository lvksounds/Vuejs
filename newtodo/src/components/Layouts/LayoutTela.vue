<template>
  <div
    id="todo-container"
    class="flex flex-col container w-96 m-auto mt-20 rounded-lg font-ubuntu font-medium shadow-xl"
  >
    <ParteSuperior @add-task="taskUpdate" @show-done-tasks="setTaskDone" />
    <ParteInferior :task-list="tasks" :filter-tasks="donedTask" />
  </div>
</template>

<script>
import ParteSuperior from "@/components/ParteSuperior.vue";
import ParteInferior from "@/components/ParteInferior.vue";

export default {
  name: "LayoutTela",
  components: { ParteInferior, ParteSuperior },
  data() {
    return {
      tasks: new Array(),
      taskNum: 0,
      donedTask: Boolean,
    };
  },
  methods: {
    taskUpdate(newTask) {
      this.tasks.unshift({
        index: this.taskNum,
        value: newTask,
        done: false,
        deleted: false,
      });
      this.taskNum++;
    },
    setTaskDone() {
      this.donedTask = true;
    },
  },
};
</script>
