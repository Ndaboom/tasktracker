<template>
<div class="container">
  <Header title="Task tracker"/>
  <Tasks @toggle-reminder="toggleReminder"
  @delete-task="deleteTask" :tasks="tasks"/>
</div>
</template>



<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
export default {
  name: 'App',
  components: {
    Header,
    Tasks,
  },
  data(){
    return {
      tasks: []
      }
  },
  methods: {
    deleteTask(id){
      if(confirm('Are you sure?')){
      this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
  },
  toggleReminder(id){
    this.tasks = this.tasks.map((task) => task.id === id ? { ...task, reminder: !task.reminder} : task) 
  },
  created(){
      this.tasks = [
        {
          id:1,
          text: 'Doctors Appointement',
          day: 'March 1st at 2:30pm',
          reminder: true,
        },
        {
          id:2,
          text: 'Allez manger',
          day: 'July 7th at 12:30pm',
          reminder: false,
        },
        {
          id:3,
          text: 'Coder',
          day: 'July 7th at 2:30pm',
          reminder: true,
        },
        ]
  },
}
</script>

<style>

</style>
