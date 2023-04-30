<template>
  <div class="format">
    <h1> {{title}} </h1>
  </div>
    
</template>
<script>
export default {
  name: 'MyHeader',
  props: {
    title: String
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


h1{
  color:white;
}

.format{
  padding: 20px;
}
</style>



