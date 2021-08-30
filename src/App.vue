<template>
  <div class="container">
    <Header title="Task Tracker"/>
    <Tasks :tasks="tasks" />
  </div>
  
</template>

<script>
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';

export default {
  name: 'App',
  components:{
    Header,
    Tasks
  },
  data(){
    return {
      tasks: [{
        id:1,
        text:"check a task",
        day:'23/08/2021',
        reminder:true
      }]
    }
  },
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
        reminder:true
      }
    ]
  }

}
</script>

<style>
.container{
  margin: 0 auto;
  padding: 10px;
  width: 500px;
  height: auto;
  border: 1px solid rgb(3, 182, 182);
}

</style>
