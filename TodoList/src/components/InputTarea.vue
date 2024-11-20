<script setup>
import { ref } from 'vue';

const newTask = ref('');
const error = ref(false);
const emit = defineEmits(['add-task']);

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
<div class="input-tarea">
<input
    v-model="newTask"
    type="text"
    placeholder="Nueva Tarea"
    @keyup.enter="addTask"
    />
    <button @click="addTask">Agregar</button>
    <p v-if="error" class="error-message">La tarea no puede estar vacia</p>
</div>



</template>
<style scoped>
.input-tarea{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 20px;
}

input{
    padding: 10px;
    width: 80%;
}

button{

    padding:10px;
    margin-left: 10px;
}
.error-message{
    color: red;
    font-size: 12px;
    margin-top: 5px;
}

</style>
