<template>
    <div class="skills-container">
        <h3>技能列表</h3>
        <div class="skill-item" v-for="(item, index) in skills" :key="index">
            <p>{{ item.name }} - 
                <span v-if="item.unLocked" style="color: red;">未解锁</span>
                <span v-else style="color:green">已解锁</span>

            </p>
        </div>
    </div>
</template>

<script setup lang="ts">
const skills = [
    {name:'七十二变',unLocked:false},
    {name:'火眼金睛',unLocked:true},
    {name:'筋斗云',unLocked:false},
]
</script>

<style scoped>
.skills-container {
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    font-family: 'Arial', sans-serif;
}

h3 {
    color: #333;
}

.skill-item {
    margin-bottom: 10px;
    padding: 10px;
    background-color: white;
    border: 1px solid #ddd;
    border-radius: 4px;
}

.skill-item p {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.unlocked {
    color: green;
    font-weight: bold;
}

.locked {
    color: red;
    font-weight: bold;
}
</style>
