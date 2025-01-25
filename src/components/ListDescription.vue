<script>
  export default {
    data() {
      return {
        newTask: '',
        tasks: [],
      };
    },
    methods: {
      addTask() {
        if (this.newTask.trim() !=='') {
          this.tasks.push({ text: this.newTask, completed: false });
          this.newTask = '';
        }
      }
    },
  };
</script>

<template>
  <div>
    <input type="text" v-model="newTask" placeholder="Que vas hacer">
    <button @click="addTask">AHORA CUMPLELO</button>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <input type="checkbox" v-model="task.completed">
        <span :class="{ completed: task.completed }">{{ task.text }}</span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.completed {
  text-decoration: line-through;
  color: gray;
}
</style>
