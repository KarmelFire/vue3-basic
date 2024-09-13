<template>
    <div>
        <div> 
            基础攻击力:
            <input v-model="baseAttack" type="number">
        </div>
        <div> 
            装备加成:
            <input v-model="gearBonus" type="number">
        </div>
        <p>总攻击力：{{ totalAttack }}</p>
    </div>
</template>

<script setup lang="ts">
import {ref, computed} from 'vue'
const baseAttack = ref<number>(50)
const gearBonus = ref<number>(20)
const totalAttack = computed(() => baseAttack.value + gearBonus.value)
</script>

<style scoped>
/* 容器样式 */
div {
    margin: 20px;
    padding: 10px;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* 输入框样式 */
input[type="number"] {
    padding: 8px;
    margin: 5px 0;
    border: 1px solid #ccc;
    border-radius: 4px;
    width: 100px;
    box-sizing: border-box; /* 确保padding不会增加输入框的总宽度 */
}

/* 输入框获得焦点时的样式 */
input[type="number"]:focus {
    outline: none;
    border-color: #007bff;
    box-shadow: 0 0 8px rgba(0, 123, 255, 0.5);
}

/* 段落样式 */
p {
    margin-top: 10px;
    font-size: 16px;
    color: #333;
}

/* 响应式设计：在小屏幕上堆叠元素 */
@media (max-width: 600px) {
    div {
        margin: 10px;
    }
    input[type="number"] {
        width: 80%;
        margin: 5px auto;
    }
}
</style>
