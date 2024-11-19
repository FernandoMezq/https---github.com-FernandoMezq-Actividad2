<script setup>
import {ref} from 'vue';

const newTask = ref('');
const error = ref(false);
const addTask = () =>{
    if (newTask.value.trim() === ''){
        error.value = true;
        return;
    }
}

</script>