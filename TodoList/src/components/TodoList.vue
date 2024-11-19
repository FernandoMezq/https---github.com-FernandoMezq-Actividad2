<script>
import InputTarea from './InputTarea.vue';
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
        
   
   
   
    </ul>

</div>




</template>

<style>


</style>