<template>
  <body>
    <div
      id="todo-container"
      class="flex flex-col container w-96 m-auto mt-20 rounded-lg font-ubuntu font-medium shadow-xl"
    >
      <ParteSuperior @add-task="taskUpdate" @filter="applyFilter" />
      <ParteInferior :new-task="task" :show-filter="taskFilter" />
    </div>
  </body>
</template>

<script>
import ParteSuperior from "@/components/ParteSuperior.vue";
import ParteInferior from "@/components/ParteInferior.vue";

export default {
  name: "LayoutTela",
  components: { ParteInferior, ParteSuperior },
  data() {
    return {
      task: "",
      taskFilter: "all",
    };
  },
  methods: {
    taskUpdate(newTask) {
      this.task = newTask;
    },
    applyFilter(newFilter) {
      this.taskFilter = newFilter;
    },
  },
};
</script>
