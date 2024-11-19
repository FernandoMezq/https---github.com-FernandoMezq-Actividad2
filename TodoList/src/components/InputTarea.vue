<script setup>
import {compile, ref} from 'vue';

const newTask = ref('');
const error = ref(false);
const addTask = () =>{
    if (newTask.value.trim() === ''){
        error.value = true;
        return;
    }
    error.value = false;
    emit('add-task',{title: newTask.value, completed: false});
    newTask.value = '';

};

</script>
<template>



    
</template>