<template>
  <form @submit.prevent="addTodo" class="flex flex-col mt-5">
    <label for="todoInput" class="font-semibold text-left mb-1">New ToDo</label>
    <input
      v-model="newTodo"
      autocomplete="off"
      id="todoInput"
      name="todoInput"
      type="text"
      class="
        bg-gray-700
        px-3
        py-3
        border-2 border-gray-400
        rounded-lg
        outline-none
        text-xl
      "
    />
    <button
      type="submit"
      class="
        mt-4
        bg-green-400
        text-gray-700
        py-4
        rounded-lg
        text-lg
        font-semibold
      "
    >
      Add ToDo
    </button>
  </form>
</template>

<script>
import { inject } from "vue";

export default {
  name: "TodoForm",

  setup() {
    const newTodo = inject("newTodo");
    const addTodo = inject("addTodo");

    return { newTodo, addTodo };
  }
};
</script>
