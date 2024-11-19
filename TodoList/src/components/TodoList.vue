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
const deleteTask = (index)  => {
    props.tasks[index].completed = !props.tasks[index].completed;
};

</script>

<template>





</template>

<style>


</style>