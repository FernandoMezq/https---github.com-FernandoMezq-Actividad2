<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    tasks:{
        type: Array,
        required: true,
    },
});
const emit = defineEmits(['toggle-task', 'delete-task']);

const toggleComplete = (index) => {
    emit('toggle-task', index);
};
const deleteTask = (index) =>{
    emit('delete-task', index);
};

</script>

<template>
<div class="todo-list">
    <h2> Tareas </h2>
    <ul>
        <li
        v-for="(task, index) in tasks"
        :key="index"
        :class="{completed: task.completed}"
        >
        <span>{{ task.title }}</span>
        <button @click="toggleComplete(index)">Completar</button>
        <button @click="deleteTask(index)">Eliminar</button>
        </li>
    </ul>
</div>




</template>

<style scoped>
.todo-list{
    margin: 20px
}
ul{
    list-style-type: none;
    padding: 0;
}
li{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10px 0;
}
button{
    margin-left: 10px;
}
.completed{
    text-decoration: line-through;
    color: red;
}
</style>