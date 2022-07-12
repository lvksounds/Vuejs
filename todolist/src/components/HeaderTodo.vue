<template>
  <div class="flex flex-row justify-center p-2">
    <h1 class="text-xl">To <span class="text-red-600">Do </span>List</h1>
    <ClipboardCheckIcon class="w-7 text-red-600" />
  </div>

  <div>
    <div class="flex flex-row border-b border-t justify-between p-2 box-border">
      <button
        class="bg-red-500 text-white w-1/3 m-1 rounded hover:bg-white hover:text-red-500 hover:border-red-500"
      >
        All
      </button>
      <button
        class="bg-red-500 text-white w-1/3 m-1 rounded hover:bg-white hover:text-red-500 hover:border-red-500"
      >
        Done
      </button>
      <button
        class="bg-red-500 text-white w-1/3 m-1 rounded hover:bg-white hover:text-red-500 hover:border-red-500"
      >
        Undone
      </button>
    </div>
  </div>
</template>

<script>
import { ClipboardCheckIcon } from "@heroicons/vue/solid";

export default {
  name: "HeaderTodo",
  components: { ClipboardCheckIcon },
};
</script>
