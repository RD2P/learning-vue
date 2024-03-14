<template>
  <header>{{ title }}</header>  
</template>

<script>
  export default {
    name: 'Header',
    props: {
      title: String,
    },
  }
</script>
