<template>
  <div
    class="flex flex-col bg-white w-96 border mt-14 ml-auto mr-auto shadow-md p-2 text rounded-sm"
  >
    <HeaderTodo />
    <TodoList />
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
};
</script>
