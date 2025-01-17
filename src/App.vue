<template>
  <div
    class="flex justify-center items-center min-h-screen bg-gradient-to-br from-blue-100 via-blue-300 to-purple-200"
  >
    <div class="bg-white shadow-2xl rounded-xl p-8 w-[500px]">
      <header class="text-2xl font-extrabold text-gray-800 mb-6 text-center">
        Task Manager
      </header>

      <TaskForm @add-task="addTask" />

      <div class="border-t my-6"></div>

      <TaskList :tasks="tasks" @delete-task="deleteTask" />
    </div>
  </div>
</template>

<script>
import TaskForm from "./components/TaskForm.vue";
import TaskList from "./components/TaskList.vue";

export default {
  components: {
    TaskForm,
    TaskList,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(newTask) {
      this.tasks.push({ text: newTask, completed: false });
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style scoped>
@media (max-width: 768px) {
  .w-[500px] {
    width: 90%;
  }
}
</style>
