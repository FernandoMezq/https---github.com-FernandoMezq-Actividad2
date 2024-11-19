<script>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    tasks:{
        type: Array,
        Required: true,
    },
});
const emit = defineEmits(['add-task']);

const toggleComplete = (index) => {
    props.tasks[index].completed = !props.tasks[index].completed;

};
const deleteTask = (index) =>{
    props.tasks.splice(index, 1);
};

</script>

<template>
<div class="todo-list">
    <h2> Tareas </h2>
    <ul>
        <li
        v-for="(task, index) in tasks"
        :key="index"
        :class="{completed:task.completed}"
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

</style>