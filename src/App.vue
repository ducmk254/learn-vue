<template>
  <div class="container">
    <Header title="Task Tracker" @toggle-add-task="toggleAddTask" />
    <AddTask v-show="showAddTask" @create-task = "addTask" :status="status" />
    <Tasks @delete-task="removeTask" @toggle-reminder="toggleReminder" :tasks="tasks" />
  </div>
  
</template>

<script>
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';
import AddTask from './components/AddTask.vue';

export default {
  name: 'App',
  components:{
    Header,
    Tasks,
    AddTask
  },
  data(){
    return {
      tasks:[],
      showAddTask:false
    }
  },
  methods:{
      removeTask(id){
          if(confirm('Are you sure ?')){
              this.tasks = this.tasks.filter(task=>task.id !== id);
          }
          //console.log(id);
      },
      toggleReminder(id){
        console.log(id);
        this.tasks = this.tasks.map(task=>task.id === id ? {...task,reminder:!task.reminder} : {...task}) 
      },
      addTask({id,text,day,reminder}){
          this.tasks = [...this.tasks,{id,text,day,reminder}];
      },
      toggleAddTask(){
        this.showAddTask = !this.showAddTask;
      }
    }
  ,
  emits:['create-task'],
  created() {
      this.tasks = [
        {
          id:1,
          text:"check a task",
          day:'23/08/2021',
          reminder:true
        },
        {
          id:2,
          text:"check a task",
          day:'23/08/2021',
          reminder:false
        },
        {
          id:3,
          text:"check a task",
          day:'23/08/2021',
          reminder:false
        },
        {
          id:4,
          text:"check a task",
          day:'23/08/2021',
          reminder:false
        }
      ]
  },
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container{
  margin: 0 auto;
  padding: 10px;
  width: 500px;
  height: auto;
  border: 1px solid rgb(3, 182, 182);
}

</style>
