<template>
  <div :class="[task.reminder ? 'reminder' : 'blue', 'task']">
    <h3>{{ task.title }}
      <span>
        <i @click="$emit('remind-task')" class="bell fa-solid fa-bell"></i>
        <i @click="$emit('delete-task')" class="fas fa-times"></i>
      </span>
    </h3>
    <p>{{task.day}}</p>
    
  </div>
</template>

<script>
  export default {
    name: 'Task',
    props: {
      task: Object
    }
  }
</script>

<style scoped>
  .fas {
    color: red;
    cursor: pointer;
  }

  .bell {
    color: green;
    margin-right: 0.5rem;
    cursor: pointer;
  }

  .bell:hover {
    opacity: 0.9;
  }

  .fas:hover {
    opacity: 0.5;
  }

  .task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
  }

  .task.reminder {
    border-left: 5px solid green;
  }

  .task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
