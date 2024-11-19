
<script setup>
import TodoList from './components/TodoList.vue';


export default{
  name:"App"
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
margin-top 25px;
}
#h1{
color: red;
font-style: italic;
}



</style>
