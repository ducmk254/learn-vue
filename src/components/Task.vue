<template>
        <div @dblclick="$emit('toggle-reminder',task.id)" :class="task.reminder ? 'item reminder' :'item' ">
            <h3>{{task.text}}
                <i @click="deleteTask(task.id)" class="fas fa-times"></i>
            </h3>
            <p>
                {{task.day}}
            </p>
        </div>
</template>

<script>
export default {
    name:'Task',
    props:{
        task: Object,
        removeTask: Function
    },
    methods:{
        deleteTask(id){
            this.$emit('delete-task',id);
        }
    }
}
</script>
<style scoped>
.item{
    background-color: rgb(219, 247, 247);
    padding: 5px 10px;
    margin: 5px 0 0 0;
}
.item h3{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    line-height: 2rem;
}
.fas{
    color: red;
    cursor: pointer;
    font-size: 0.8rem;

}
.reminder{
    border-left: 3px solid green;
}
</style>