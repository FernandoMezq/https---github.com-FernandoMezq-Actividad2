
<script setup>
import TodoList from './components/TodoList.vue';
import InputTarea from './components/InputTarea.vue';
import { ref } from 'vue';

const tasks = ref([]);

const addNewTask = (tasks)=>{
  tasks.value.push(task);
};
</script>


<template>
  <div id="app">
    <h1>Lista de Tareas</h1>
    <!-- Aqui es donde integrar los componentes-->
    <TodoList/>
  </div>
</template>

<style scoped>
#app{
  
font-family: 'Times New Roman', Times, serif;
text-align: center;

};
#h1{
color: red

};


</style>
