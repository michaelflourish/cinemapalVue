<template>
    <div class="overlay">
        <h2>{{ item.title }}</h2>
        <h3>{{ item.description }}</h3>
        <p>Genre: {{ item.genre }}</p>
        <p>PG Rating: {{ item.pgRating }}</p>
        <p>Year: {{ item.year }}</p>
    </div>
</template>

<script>

export default{
    name: 'SingleMovie',
    props:{
        item: Array
    }
}
</script>

<style scoped>

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #fff;
  text-align: center;
  z-index: 2;
  opacity: 0;
  transition: all 0.3s ease-in-out;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
}


.square:hover .overlay,
.square.active .overlay,
.square.expanded .overlay {
  opacity: 1;
}

</style>