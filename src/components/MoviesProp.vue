<template>
  <div>
    <div v-for="(row, rowIndex) in rows" :key="rowIndex" class="row">
      <div v-for="(item, itemIndex) in row" :key="itemIndex" class="square" :class="{ active: activeIndex === rowIndex * 4 + itemIndex, expanded: expandedSquare === rowIndex * 4 + itemIndex }"
        @click="expandedSquare === rowIndex * 4 + itemIndex ? expandSquare(-1) : expandSquare(rowIndex * 4 + itemIndex)">
        <img v-bind:src="item.imageUrl" alt="Movie Image" class="movie-image">
        <SingleMovie :item="item"/>
      </div>
    </div>
  </div>
</template>

<script>
import SingleMovie from "./SingleMovie.vue"

export default {
  name: 'MoviesProp',
  data() {
    return {
      activeIndex: -1,
      expandedSquare: -1,
      items: [],
      rows: []
    }
  },
  methods: {
    expandSquare(index) {
      if (index === this.expandedSquare) {
        // Square is already expanded, so collapse it
        this.expandedSquare = -1;
      } else {
        // Expand the clicked square
        this.expandedSquare = index;
      }
    },
  },
  props: {
    msg: String,
    row: Array
  },
  components: {
        SingleMovie
    },
  created() {
    // Fetch movies from https://cinemapalapp.herokuapp.com/api
    fetch('https://cinemapalapp.herokuapp.com/api')
      .then(response => response.json())
      .then(movies => {
        // Divide movies into rows of 4 items each
        this.items = movies;
        this.rows = movies.reduce((resultArray, item, index) => {
          const chunkIndex = Math.floor(index / 4);

          if (!resultArray[chunkIndex]) {
            resultArray[chunkIndex] = [] // start a new row
          }

          resultArray[chunkIndex].push(item)

          return resultArray
        }, []);
      });
  }
}
</script>

<style scoped>

.row {
  display: flex;
  justify-content: space-between;
}

.square {
  flex-basis: calc(25% - 40px);
  height: 400px;
  background-color: #F8C391;
  border-radius: 10px;
  margin-right: 20px;
  margin-bottom: 50px;
  margin-left: 50px;
  margin-right: 50px;
  transition: all 0.3s ease-in-out;
  overflow: hidden;
  text-align: center;
  position: relative;
}

.movie-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0.8;
  z-index: 1;
}


.expanded {
  flex-basis: 100%;
  height: 600px;
}


@media (max-width: 600px) {
  .row {
    flex-wrap: wrap;
  }

  .square {
    flex-basis: 100%;
    height: 300px;
    margin-bottom: 20px;
  }
}

@media (max-width: 767px) { /* Mobile Devices (Portrait) */
  .row {
    flex-wrap: wrap;
  }

  .square {
    flex-basis: 100%;
    height: 300px;
    margin-bottom: 20px;
    margin-left: 0;
    margin-right: 0;
  }
}

@media (min-width: 768px) and (max-width: 1023px) { /* Tablets (Portrait) */
  .row {
    flex-wrap: wrap;
  }

  .square {
    flex-basis: calc(50% - 40px);
    height: 350px;
    margin-bottom: 30px;
    margin-left: 20px;
    margin-right: 20px;
  }
}

@media (min-width: 1024px) and (max-width: 1199px) { /* iPad (landscape) */
  .row {
    flex-wrap: wrap;
  }

  .square {
    flex-basis: calc(50% - 40px);
    height: 350px;
    margin-bottom: 30px;
    margin-left: 20px;
    margin-right: 20px;
  }
}







</style>