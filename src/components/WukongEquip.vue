<template>
    <div class="equipment-manager">
      <h2>装备管理</h2>
      <div class="input-group">
        <input type="text" placeholder="输入装备名称" v-model="newEquip" class="form-control">
        <button @click="addEquip" class="btn-add">添加装备</button>
      </div>
      <div class="equipment-list">
        <div v-for="(item, index) in equipList" :key="index" class="equipment-item">
          {{ item }}
          <button @click="deleteEquip(index)" class="btn-delete">删除</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  const equipList = ref<string[]>([]);
  const newEquip = ref('');
  const addEquip = () => {
    if (newEquip.value.trim() !== '') {
      equipList.value.push(newEquip.value.trim());
      newEquip.value = '';
    }
  };
  const deleteEquip = (index) => {
    equipList.value.splice(index, 1);
  };
  </script>
  
  <style scoped>
  .equipment-manager {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .input-group {
    display: flex;
    margin-bottom: 20px;
  }
  
  .form-control {
    flex: 1;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px 0 0 4px;
    font-size: 16px;
  }
  
  .btn-add {
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 0 4px 4px 0;
    cursor: pointer;
    font-size: 16px;
  }
  
  .btn-add:hover {
    background-color: #0056b3;
  }
  
  .equipment-list {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  .equipment-item {
    padding: 10px;
    border: 1px solid #eee;
    border-radius: 4px;
    margin-bottom: -1px; /* Remove double border between list items */
    background-color: #f9f9f9;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .btn-delete {
    padding: 5px 10px;
    background-color: #dc3545;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
  }
  
  .btn-delete:hover {
    background-color: #c82333;
  }
  </style>