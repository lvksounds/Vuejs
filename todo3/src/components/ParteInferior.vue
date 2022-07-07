<template>
  <div id="container-newtasks" class="m-3 flex flex-col">
    <div v-for="task in taskList" :key="task.index">
      <div
        id="tasks"
        class="flex flex-row justify-between border-b border-indigo-500 p-2"
        v-if="!task.removed"
      >
        <p id="task-text" :class="{ 'line-through': task.done }">
          {{ task.value }}
        </p>
        <div id="task-buttons" class="flex flex-row">
          <button @click="task.done = !task.done">
            <XIcon class="h-5/6 w-6 text-red-500" v-if="task.done" />
            <CheckIcon class="h-5/6 w-6 text-green-500" id="delBtn" v-else />
          </button>
          <button @click="task.removed = !task.removed" v-if="!task.removed">
            <TrashIcon
              class="h-5/6 w-5"
              :class="{ 'text-red-600': task.removed }"
              id="chkBtn"
            />
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
  components: { CheckIcon, TrashIcon, XIcon },
  props: { taskList: Array },
};
</script>
