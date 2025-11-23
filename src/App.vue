<script setup>
import { ref } from 'vue';

const tasks = ref([]);
const newTask = ref('');

const addTask = () => {
  if (newTask.value.trim() !== '') {
    tasks.value.push(newTask.value);
    newTask.value = '';
  }
};

const deleteTask = (index) => {
  tasks.value.splice(index, 1);
};
</script>

<template>
  <div class="container">
    <div class="card">
      <h2 class="title">✨🌸 My To-Do List 🎀✨</h2>

      <form @submit.prevent="addTask" class="input-group">
        <input
          v-model="newTask"
          type="text"
          placeholder="Mau melakukan apa hari ini?..."
          class="task-input"
        />
        <button type="submit" class="add-btn">Tambah</button>
      </form>

      <div v-if="tasks.length === 0" class="empty-state">
        Belum ada tugas hari ini cantik 💕
      </div>

      <ul v-else class="task-list">
        <li v-for="(task, index) in tasks" :key="index" class="task-item">
          <span class="task-text">{{ task }}</span>
          <button @click="deleteTask(index)" class="delete-btn">Hapus</button>
        </li>
      </ul>

    </div>
  </div>
</template>

<style scoped>
.container {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  display: flex;
  justify-content: center;
  padding-top: 50px;
  min-height: 100vh;
  background-color: #fff0f5;
}

.card {
  background: #ffffff;
  width: 100%;
  max-width: 480px;
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 8px 25px rgba(255, 105, 180, 0.2);
  border: 2px solid #ffc1e3;
}

.title {
  text-align: center;
  color: #d81b60;
  margin-bottom: 25px;
  font-size: 1.8rem;
}

.input-group {
  display: flex;
  gap: 10px;
  margin-bottom: 25px;
}

.task-input {
  flex: 1;
  padding: 12px 15px;
  border: 2px solid #ffc1e3;
  border-radius: 12px;
  font-size: 1rem;
  outline: none;
  transition: border-color 0.3s;
}

.task-input:focus {
  border-color: #ff69b4;
}

.add-btn {
  padding: 12px 24px;
  background-color: #ff69b4;
  color: white;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 600;
  transition: background-color 0.3s, transform 0.2s;
}

.add-btn:hover {
  background-color: #e05297;
  transform: translateY(-2px);
}

.empty-state {
  text-align: center;
  color: #f06292;
  padding: 25px;
  font-style: italic;
  background-color: #fff5f8;
  border-radius: 12px;
  border: 1px dashed #ffc1e3;
}

.task-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.task-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px;
  margin-bottom: 10px;
  background-color: #fff;
  border: 1px solid #ffe4e1;
  border-radius: 12px;
  transition: all 0.3s;
}

.task-item:hover {
  box-shadow: 0 4px 12px rgba(255, 182, 193, 0.3);
  border-color: #ffb6c1;
}

.task-text {
  color: #880e4f;
  font-size: 1.05rem;
}

.delete-btn {
  background-color: #f50057;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 0.9rem;
  font-weight: 600;
  transition: background-color 0.3s;
}

.delete-btn:hover {
  background-color: #c51162;
}
</style>