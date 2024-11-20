
<script setup>
import TodoList from './components/TodoList.vue';
import InputTarea from './components/InputTarea.vue';
import { ref } from 'vue';

const tasks = ref([]);

const addNewTask = (task)=>{
  tasks.value.push(task);
};

const toggleTask = (index) =>{
  tasks.value[index].completed = !tasks.value[index].completed;

};
const deleteTask = (index) => {
  tasks.value.splice(index, 1);

};

</script>


<template>
 <div id="app">
    <h1>Lista de Tareas</h1>
    <InputTarea @add-task="addNewTask" />
    <!-- Integrar el componente TodoList -->
    <TodoList 
  :tasks="tasks" 
  @toggle-task="toggleTask" 
  @delete-task="deleteTask" 
/>
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
