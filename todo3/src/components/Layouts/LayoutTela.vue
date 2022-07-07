<template>
  <div
    id="todo-container"
    class="flex flex-col container w-96 m-auto mt-20 rounded-lg font-ubuntu font-medium shadow-xl"
  >
    <ParteSuperior @add-task="updateTask" />
    <ParteInferior :task-list="tasks" />
  </div>
</template>

<script>
import ParteSuperior from "@/components/ParteSuperior.vue";
import ParteInferior from "@/components/ParteInferior.vue";
export default {
  name: "LayoutTela",
  components: { ParteSuperior, ParteInferior },
  data() {
    return {
      tasks: new Array(),
      taskNum: 0,
    };
  },
  methods: {
    updateTask(newTask) {
      this.tasks.push({
        index: this.taskNum,
        value: newTask,
        done: false,
        removed: false,
      });
      this.taskNum++;
    },
  },
};
</script>
