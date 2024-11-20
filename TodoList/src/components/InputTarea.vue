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
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}
button:hover{
    background-color: #0056b3;
}
.error-message{
    color: red;
    font-size: 12px;
    margin-top: 5px;
    text-align: left;
}

</style>
