<template>
  <div class="container mx-auto">
    <div class="flex justify-center items-center py-10 my-5">
      <div class="p-8 bg-green-300 shadow-md rounded w-fit">
        <h2 class="text-xl text-center text-white">Add a task</h2>
        <input
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
        class="
          p-8
          mx-4
          bg-gray-100
          shadow-md
          rounded
          flex
          items-center
          justify-between
        "
      >
        <div>
          <div>1 Todos</div>
          <div class="text-gray-500 text-sm">test</div>
        </div>
        <div class="space-x-6">
          <button class="px-2 text-red-400">
            <i class="fas fa-trash"></i>
          </button>
          <button class="px-2 text-green-400">
            <i class="fas fa-check"></i>
          </button>
          <button class="px-2 text-yellow-400">
            <i class="fas fa-undo"></i>
          </button>
        </div>
      </div>

      <div
        class="
          px-8
          py-6
          bg-gray-100
          text-gray-700
          shadow-md
          rounded
          text-sm
          mt-5
          mx-4
        "
      >
        You don't have any tasks.
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "Todos",
};

</script>
