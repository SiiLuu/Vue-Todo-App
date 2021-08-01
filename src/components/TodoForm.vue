<template>
  <form class="flex flex-col mt-5">
    <label for="todoInput" class="font-semibold text-left mb-1">New ToDo</label>
    <input
      id="todoInput"
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
export default {
  name: "TodoForm"
};
</script>
