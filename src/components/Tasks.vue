<template>
    <div class="list-item" :for="task in tasks" >
        <Task :task="task"/>       
    </div>
</template>

<script>
import Task from './Task.vue';

export default {
    name:'Tasks',
    props:{
        tasks:Array
    },
    components:{
        Task
    }
}
</script>
<style scoped>

</style>