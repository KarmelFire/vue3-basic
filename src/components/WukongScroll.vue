<template>
    <div class="container">
      <button @click="scrolllToSkills" class="scroll-button">滚动到技能展示</button>
      <div class="content">
        <div ref="skillsSection" class="skills-section"></div>
        <h2 class="skills-title">技能展示</h2>
        <p class="skills-description">技能详细内容...</p>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  const skillsSection = ref<HTMLElement | null>(null);
  const scrolllToSkills = () => {
    skillsSection.value?.scrollIntoView({ behavior: 'smooth' });
  };
  </script>
  
  <style scoped>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 50px;
    min-height: 100vh;
  }
  
  .scroll-button {
    padding: 10px 20px;
    margin: 20px;
    font-size: 16px;
    border: none;
    border-radius: 5px;
    background-color: #007bff;
    color: white;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .scroll-button:hover {
    background-color: #0056b3;
  }
  
  .content {
    width: 100%;
    max-width: 800px;
    flex-grow: 1;
  }
  
  .skills-section {
    height: 600px; /* Adjust this value to create more scroll space */
    background-color: #f0f0f0;
    margin-bottom: 20px;
  }
  
  .skills-title {
    margin-bottom: 10px;
    font-size: 24px;
    color: #333;
  }
  
  .skills-description {
    font-size: 16px;
    color: #666;
    line-height: 1.6;
  }
  </style>