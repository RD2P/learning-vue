<template>
  <div v-for="task in tasks" v-bind:key="task.id">
    <Task 
      :task="task" 
      @delete-task="$emit('delete-task', task.id)" 
      @remind-task="$emit('remind-task', task.id)" 
      />
    </div>
</template>

<script>

  import Task from "./Task.vue"
  export default {
    name: 'Tasks',
    props: {
      tasks: Array
    },
    components: {
      Task  
    },
    emits: ['delete-task', 'remind-task'],
  }
</script>