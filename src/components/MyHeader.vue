<template>
    <div class="header">
      <h1>{{ Name }}</h1>
      
    </div>
  </template>
  
  <script>
  export default {
    props: {
      Name: {
        type: String,
        required: true,
      },
     
    },
  };
  </script>
  
  <style scoped>
  .header {
    background-color: #1a237e;
    text-align: center;
    padding: 1em;
  }
  .header h1{
    color: white;
  }
  </style>
  
  
