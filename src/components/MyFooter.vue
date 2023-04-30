<template>
  <footer>
    <div class="container">
      <p>&copy; 2023 CinePal. All rights reserved.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'MyFooter',
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
footer {
  background-color: #333;
  color: #fff;
  padding: 20px 0;
}

.container {
  max-width: 960px;
  margin: 0 auto;
  text-align: center;
}

@media screen and (max-width: 768px) {
  footer {
    padding: 20px;
  }
}

</style>



