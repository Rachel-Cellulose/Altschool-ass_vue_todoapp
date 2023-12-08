<template>
  <div class="completed-tasks">
    <h2>Completed Tasks</h2>
    <ul>
      <li v-for="completedTask in completedTasks" :key="completedTask.id">
        {{ completedTask.title }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    completedTasks: Array,
  },
};
</script>

<style>
.completed-tasks {
  background-color: #f0f0f0;
  padding: 15px;
  border-radius: 8px;
  margin-top: 20px;
}
</style>
