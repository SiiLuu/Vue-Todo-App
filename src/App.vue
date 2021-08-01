<template>
  <div class="min-h-screen bg-gray-700 text-center text-white py-10 px-4">
    <h1 class="text-3xl font-bold">ToDo App</h1>
    <TodoForm />
    <TodoList />
  </div>
</template>

<script>
import TodoForm from "@/components/TodoForm.vue";
import TodoList from "@/components/TodoList.vue";

export default {
  name: "App",
  components: {
    TodoForm,
    TodoList
  }
};
</script>
