<template>
    <header >
        <h1>{{title}}</h1>
        <Button @toggle-add-task="$emit('toggle-add-task')" name="Add task" @click="onClick"></Button>
    </header>
</template>

<script>
import Button from './Button.vue'

export default {
    name:'Header',
    props:{
        title:{
            type: String,
            default:'HelloWorld'
        },
        showAddTask:Boolean
    }
    ,
    components:{
        Button
    }
}
</script>
<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>
