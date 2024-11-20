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
                <th style="text-align: right;">Acciones</th>
            </tr>
        </thead>
   
        <tbody>
            <tr v-for="(task, index) in tasks"
            :key="index"
            :class="{completed: task.completed}">
                <td>{{ task.title }}</td>
                <td>
                    <div class="action-buttons">
                        <button class="toggle-task" @click="toggleComplete(index)">Completar</button>
                        <button class="delete-task" @click="deleteTask(index)">Eliminar</button>
                    </div>    
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

th,td{
    padding: 10px;
    text-align: center;
    border: 1px solid #35a;
}

td{text-align: left;}

tr{
    background-color: #f9f9f9;
}

.action-buttons{
display: flex;
justify-content: flex-end;
gap: 10px;
};

button{
    padding: 8px 12px;
    font-size: 14px;
    cursor: pointer;
    border: none;

}
.completed{
    text-decoration: line-through;
    color: red;
}




</style>