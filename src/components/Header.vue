<template>
  <header>
    <h1>{{ title }}</h1>
    <Button text="New Task" color="green" @clicked="$emit('show-add-task')"/>  
  </header>
</template>

<script>
import Button from './Button.vue'
  export default {
    name: 'Header',
    props: {
      title: String,
    },
    components: {
      Button
    },
    emits: ['show-add-task']
  }
</script>

<style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

</style>