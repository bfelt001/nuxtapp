<template>
  <div>
    <div class="container">
      <h1>Welcome to my movie website!</h1>
      <p>Search for a film here.</p>
      <form id="movieForm" autocomplete="off" @submit.prevent="searchMovie">
        <div class="form-group">
          <label for="movie">Movie Name</label>
          <input class="form-control" type="text" id="movie" placeholder="Type movie name here" v-model="searchTerm">
        </div>
        <div class="form-group">
          <button class="btn btn-block btn-outline-primary" data-bs-toggle="tooltip" data-bs-placement="right" title="Click here" type="submit">
            Search Movie
          </button>
        </div>
      </form>

      <div id="result">
        <div class="card" v-for="movie in movies" :key="movie.imdbID">
          <img :src="movie.Poster" class="card-img-top" style="width: 8rem;" alt="movie poster">
          <div class="card-body">
            <h5 class="card-title">{{ movie.Title }}</h5>
            <p class="card-text">{{ movie.Year }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movies: [],
      searchTerm: '',
    };
  },
  methods: {
    searchMovie() {
      const apiKey = '86aac794'; // my API key
      const url = `http://www.omdbapi.com/?apikey=${apiKey}&s=${this.searchTerm}&type=movie`;

      fetch(url)
        .then((response) => response.json())
        .then((data) => {
          if (data.Search) {
            this.movies = data.Search;
          } else {
            this.movies = [];
          }
        })
        .catch((error) => console.error(error));
    },
  },
  head() {
      return {
        title: this.title,
        meta: [
          // hid is used as unique identifier. Do not use `vmid` for it as it will not work
          {
            hid: 'description',
            name: 'description',
            content: 'This is a website about movies and movie lovers. Users can search for movies and posters.'
          }
        ]
      }
    },
};
</script>

<style>
.container {
  max-width: 75%;
  margin: 0 auto;
  padding: 8rem 1rem 0 0;
}
</style>