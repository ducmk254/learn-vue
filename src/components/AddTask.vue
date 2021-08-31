<template>
    <form @submit="onSubmit" class="add-task">
        <input v-model="text" name='text' class="add-task__item" type="text" placeholder="Enter a task" />
        <input v-model="day" name="day" class="add-task__item" type="date" placeholder="Add day"  />
        <div class="add-task__item">
            <label for="reminder" class="flag">Set reminder</label>
            <input v-model="reminder" name='reminder'  type="checkbox" />    
        </div>
        
        <Button name="Save task" class="add-task__item" type="submit" />
    </form>
</template>

<script>
import Button from './Button.vue';

export default {
    name:'AddTask',
    components:{
        Button
    },
    data(){
        return {
            text:'',
            day:'',
            reminder:false,
            status:true
        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault();
            if(!this.text){
                alert("Please enter a task name!!!");
                return;
            }
            this.$emit('create-task',{id:Math.floor(Math.random())*100000,text:this.text,day:this.day,reminder:this.reminder});

            this.text='';
            this.day="";
            this.reminder=false;
        }
    }
}
</script>

<style scoped>
.add-task{
    
    border: 1px solid red;
    padding: 5px 10px;
    display: flex;
    flex-direction: column;
}
.add-task__item{
    margin: 5px 0;
    padding: 5px;

    outline: none;
}
.flag{
    margin-right: 10px;
}
</style>

