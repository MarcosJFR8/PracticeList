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
    <input class="taskWriter" type="text" v-model="newTask" placeholder="Que vas hacer">
    <button class="itemButton" @click="addTask">AHORA CUMPLELO</button>
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

.itemButton {
  background-color: var(--card-bg-color);
  color: var(--text-color);
  border: 1px solid var(--text-color);
  margin: 10px 80px 20px;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
  position: relative;
  top: 200px;
  left: 6cm;
  border: 2px solid rgb(95 97 110);
  border-radius: 0.5cm;
  align-items: center;
  justify-content: center;
} 

.taskWriter {
  position: relative;
  top: 200px;
  left: 6cm;
  width: 30%;
  height: 30px;
  border: 2px solid rgb(95 97 110);
  border-radius: 0.5cm;
  padding: 5px;
  margin: 20px 20px 20px;
}

ul{
  list-style: none;
  padding: 0;
  position: fixed;
  top: 170px;
  left: 0;
  width: 100%;  
  margin: 2%; 
}
</style>
