<template>
  <div class="container mx-auto">
    <div class="flex justify-center items-center py-10 my-5">
      <div class="p-8 bg-green-300 shadow-md rounded w-fit">
        <h2 class="text-xl text-center text-white">Add a task</h2>
        <input
          v-model="todoText"
          @keydown.enter="addTodo"
          type="text"
          class="p-2 mt-4 border rounded w-full outline-none"
        />
      </div>
    </div>

    <h1 class="py-8 text-2xl text-center font-bold text-gray-700">
      Tasks List
    </h1>

    <div class="py-4 px-4 mx-2">
      <div
        v-for="(todo, index) in todos"
        :key="index"
        :class="{'bg-green-100': todo.done}"
        class="
          p-8
          mx-2
          my-2
          bg-gray-100
          shadow-md
          rounded
          flex
          items-center
          justify-between
        "
      >
        <div class="container mx-auto">
          <div>{{ todo.text }}</div>
          <div class="text-gray-500 text-sm">{{ todo.createdAt.toString() }}
          </div>
        </div>
        <div class="flex">
          <button 
            class="px-6 text-red-400" 
            title="Remove todo">
            <i class="fas fa-trash"></i>
          </button>
          <button 
            v-if="!todo.done"
            @click="markAsDone(index)" 
            class="px-2 text-green-400" 
            title="Mark as done">
            <i class="fas fa-check"></i>
          </button>
          <button 
            v-else
            @click="markAsUndone(index)"
            class="px-2 text-yellow-400" 
            title="Mark as undone">
            <i class="fas fa-undo"></i>
          </button>
        </div>
      </div>

      <div
        v-if="todos.length === 0"
        class="
          px-8
          py-6
          bg-gray-100
          text-gray-700
          shadow-md
          rounded
          text-sm text-center
          m-auto
        "
      >
        You don't have any tasks.
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent, reactive, ref } from "@vue/runtime-core";

export default defineComponent({
  setup() {
    const todos = reactive([]);
    const todoText = ref("");

    function addTodo() {
      todos.unshift({
        text: todoText.value,
        createdAt: new Date(),
        done: false,
      });

      todoText.value = "";
    }

    function markAsDone(index) {
      todos[index].done = true;
    }

    function markAsUndone(index) {
      todos[index].done = false;
    }

    return {
      todos,
      todoText,
      addTodo,
      markAsDone,
      markAsUndone,
    };
  },
});
</script>
