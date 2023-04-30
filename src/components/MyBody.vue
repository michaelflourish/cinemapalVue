<template>
    <div>
      <h1>{{ project }}</h1>
      <h2>{{ creator }}</h2>
      <h3>{{ crn }}</h3>
      <h3>{{ sid }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MyBody',
    props: {
      project: String,
      creator: String,
      crn: String,
      sid: String
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  
  h1, h2, h3 {
    color:white;
  }


  </style>
  
  
  
  