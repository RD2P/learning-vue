<template>
  <div>
    <h3>{{ task.title }}</h3>
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

</style>
