<script>
export default {
  data() {
    return {
      movies: [],
      image: [],
      query: ''
    }
  },
  mounted() {
    this.fetchUserMovie();
  },
  methods: {
    fetchUserMovie() {
      fetch('http://www.omdbapi.com/?apikey=dc43bd63&t=' + this.query)
        .then(response => response.json())
        .then(data => {
          this.movies.push(data);
          this.image = (data.Poster)
          console.log(this.movies);
        });
    },
    clearMovies() {
      this.movies = [];
      this.query = '';
    }
  }
}

</script>

<template>
  <div class="movies">
    <div class="movie-input">
      <input v-model="query" type="text" />
      <button type="submit" @click="fetchUserMovie" id="searchBtn">Search</button>
      <button type="submit" @click="clearMovies" id="clearBtn">Clear</button>
    </div>
    <div class="movie-results">
      <ul v-for="movie in movies" v-bind:key="movie.imdbID">
        <li>{{ movie.Title }}</li>
        <p>{{ movie.Year }}</p>
        <img :src='image' />
      </ul>
    </div>
  </div>
</template>


<style scoped>
  .movies {
    display: flex;
    align-items: center;
    flex-direction: column;
    height: 100vh;
    margin-top: 100px;
  }
  .movie-input {
    margin-bottom: 20px;
  }
  img {
    max-height: 200px;  
  }
  ul li {
    list-style-type: none;
  }
  #clearBtn {
    background-color: brown;
    color: white;
    padding: 5px;
    margin-left: 10px;
  }
  #searchBtn {
    background-color: rgb(11, 11, 97);
    color: white;
    padding: 5px;
    margin-left: 10px;
  }
  input {
    padding: 5px;
  }
  .movie-results {
    display: flex;
    flex-wrap: wrap;
  }
</style>
