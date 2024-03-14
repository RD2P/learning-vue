<template>
  <button @click="onClick()" :style="{background:color}">{{ text }}</button>
</template>

<script>

  export default {
    name: 'Button',
    props: {
      text: String,
      color: String
    },
    methods: {
      onClick(){
        console.log("Clicked " + this.text)
      }
    }
  }
</script>

<style scoped>
  button {
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    color: white;
  }

  button:hover {
    opacity: 0.9;
  }
</style>
