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
    <table>
        <thead>
            <tr>
                <th>Tarea</th>
                <th>Acciones</th>
            </tr>
        </thead>
   
        <tbody>
            <tr v-for="(task, index) in tasks"
            :key="index"
            :class="{completed: task.completed}">
                <td>{{ task.title }}</td>
                <td>
                    <button class="toggle-task" @click="toggleComplete(index)">Completar</button>
                    <button class="delete-task" @click="deleteTask(index)">Eliminar</button>
                </td>        
            </tr>
        </tbody>
    </table>
</div>
</template>

<style scoped>
.todo-list{
    margin: 20px;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

h2{
    margin-bottom: 15px;
    font-size: 1.5em;
}

ul{ width: 100%;
    border-collapse: collapse;

};
ol


button{
    margin-left: 10px;
}
.completed{
    text-decoration: line-through;
    color: red;
}
</style>