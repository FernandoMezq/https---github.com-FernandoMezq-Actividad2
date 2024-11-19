
<script setup>
import TodoList from './components/TodoList.vue';


export default {
  name: 'App',
  components: {
    TodoList
  }
};

</script>


<template>
  <div id="app">
    <h1>Lista de Tareas</h1>
    <TodoList/>
  </div>
</template>

<style scoped>
#app{
font-family: 'Times New Roman', Times, serif;
text-align: center;
margin-top 25px;
}



</style>
