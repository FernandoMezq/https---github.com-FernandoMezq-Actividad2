
<script setup>
import TodoList from './components/TodoList.vue';
import InputTarea from './components/InputTarea.vue';
import { ref } from 'vue';

const tasks = ref([]);

const addNewTask = (task)=>{
  tasks.value.push(task);
};
</script>


<template>
  <div id="app">
    <h1>Lista de Tareas</h1>
    <InputTarea @add-task="addNewTask"/>
    <!-- Aqui es donde integrar los componentes-->
    <TodoList :tasks="tasks"/>
  </div>
</template>

<style scoped>
#app{
  
font-family: 'Times New Roman', Times, serif;
text-align: center;

};
h1{
color: #f00;


};


</style>
