<template>
  <div
    class="flex flex-col bg-white w-96 border mt-14 ml-auto mr-auto shadow-md p-2 text rounded-sm"
  >
    <HeaderTodo @send-task="receiveTask" @filter="applyFilter" />
    <TodoList :new-task="received_task" :showFilter="taskFilter" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList.vue";
import HeaderTodo from "@/components/HeaderTodo.vue";
export default {
  name: "LayoutTodo",
  components: {
    TodoList,
    HeaderTodo,
  },
  data() {
    return {
      received_task: "",
      taskFilter: "all",
    };
  },
  methods: {
    receiveTask(task) {
      this.received_task = task;
    },
    applyFilter(newFilter) {
      this.taskFilter = newFilter;
    },
  },
};
</script>
