<template>
  <div class="flex gap-2">
    <input
      v-model="newTask"
      type="text"
      placeholder="Enter a new task"
      class="flex-1 px-4 py-2 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-blue-500"
    />
    <button
      @click="submitTask"
      class="px-4 py-2 bg-blue-400 text-white rounded hover:bg-blue-600 transition"
    >
      Add
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
    };
  },
  methods: {
    submitTask() {
      if (this.newTask.trim()) {
        this.$emit("add-task", this.newTask);
        this.newTask = ""; // Clear input after adding
      }
    },
  },
};
</script>
