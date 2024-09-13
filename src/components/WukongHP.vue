<template>
    <div>
        <p>血量: {{ hp }} / 100 ({{ hpPercentage }}%)</p>
        <div class="health-bar-container">
            <div class="health-bar" :style="{ width: hpPercentage + '%' }"></div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const hp = ref(70)
const hpPercentage = computed(() => hp.value / 100 * 100)
</script>

<style scoped>
.health-bar-container {
    width: 100%; /* 容器宽度 */
    height: 20px; /* 容器高度 */
    background-color: #f9f9f9; /* 容器背景色 */
    border: 1px solid #ccc; /* 容器边框 */
    position: relative; /* 相对定位 */
    border-radius: 10px; /* 圆角 */
    overflow: hidden; /* 隐藏溢出 */
}

.health-bar {
    height: 100%; /* 血量条高度 */
    background-color: green; /* 血量条颜色 */
    transition: width 0.3s ease; /* 平滑过渡效果 */
}
</style>