<script>
import InputTarea from './InputTarea.vue';

export default{
    name: 'TodoList',
    components:{
        InputTarea
    },
data(){
    return{
        tasks:[]
    };
},
methods:{
    addTask(){
        if(this.newTask.trim() ===''){
            this.console.error = 'El titulo de la tarea no puede estar vacio';
            return;
        }
        }
    }
}
}


</script>

<template>





</template>

<style>


</style>