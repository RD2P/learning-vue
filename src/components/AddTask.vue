<template>
  <div>
    <p>Task name</p>
    <input type='text' placeholder="Task name"/>
    <p>Date</p>
    <input type='text' placeholder="Date"/><br>
    <span>Reminder</span>
    <input type='checkbox' placeholder="Task name"/>
  </div>
</template>

<script>
  export default {
    name: 'AddTask'
  }
</script>

<style scoped>
  div {
    border: 1px black solid;
    margin: 0.5rem;
    padding: 0.5rem;
  }
</style>
