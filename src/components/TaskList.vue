<template>
  <div>
    <ul class="space-y-2">
      <li
        v-for="(task, index) in tasks"
        :key="index"
        class="flex justify-between items-center bg-gray-50 p-3 rounded border border-gray-200"
      >
        <span class="text-gray-800">{{ task.text }}</span>
        <button
          @click="$emit('delete-task', index)"
          class="px-2 py-1 text-sm bg-red-400 text-white rounded hover:bg-red-600 transition"
        >
          Delete
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
};
</script>
