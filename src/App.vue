<template>
  <div class="flex min-h-screen bg-gray-700 text-center text-white py-10 px-4">
    <div class="mx-auto w-full md:w-10/12 xl:w-5/12">
      <h1 class="text-3xl font-bold">ToDo App</h1>
      <TodoForm />
      <TodoList />
    </div>
  </div>
</template>

<script>
import { ref, provide } from "vue";

import TodoForm from "@/components/TodoForm.vue";
import TodoList from "@/components/TodoList.vue";

export default {
  name: "App",

  components: {
    TodoForm,
    TodoList
  },

  setup() {
    const newTodo = ref("");
    const todos = ref([]);

    function addTodo() {
      todos.value.push({ done: false, name: newTodo.value });
      newTodo.value = "";
    }

    function removeTodo(index) {
      todos.value.splice(index, 1);
    }

    function doneTodo(todo) {
      todo.done = !todo.done;
    }

    provide("newTodo", newTodo);
    provide("todos", todos);
    provide("addTodo", addTodo);
    provide("removeTodo", removeTodo);
    provide("doneTodo", doneTodo);
  }
};
</script>
