<template>
  <div class="mt-5">
    <h1 class="text-2xl font-bold text-left">ToDo List</h1>
    <hr class="mt-1 border border-gray-400 rounded-full" />
    <ul>
      <li
        @click="doneTodo(todo)"
        v-for="(todo, index) in todos"
        :key="index"
        class="
          bg-gray-700
          px-5
          py-3
          border-2 border-gray-400
          rounded-lg
          text-lg
          mt-3
          flex
          cursor-pointer
        "
      >
        <span
          :class="todo.done && 'line-through'"
          class="ml-0 mr-auto my-auto"
          >{{ todo.name }}</span
        >
        <button
          @click.stop="removeTodo(index)"
          class="text-gray-700 bg-green-400 font-semibold px-3 py-1 rounded-md"
        >
          Remove
        </button>
      </li>
    </ul>
    <p v-if="todos.length <= 0" class="mt-10 text-gray-400 font-bold text-lg">
      Empty list.
    </p>
  </div>
</template>

<script>
import { inject } from "vue";

export default {
  name: "TodoList",

  setup() {
    const todos = inject("todos");
    const removeTodo = inject("removeTodo");
    const doneTodo = inject("doneTodo");

    return { todos, removeTodo, doneTodo };
  }
};
</script>
