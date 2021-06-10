<template>
  <div id="app">
    <div id="nav">
      <router-link :to="{ name: 'Home', query: { movies } }">Home</router-link>
      | <router-link :to="{ name: 'Random', query: { movies } }"> Random</router-link> |
      <router-link :to="{ name: 'MyMovieList', query: { movies } }">MyMovieList</router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  data: function () {
    return {
      movies: [],
    };
  },
  methods: {
    getMovies() {
      const MOVIE_URL = "https://gist.githubusercontent.com/eduChange-hphk/d9acb9fcfaa6ece53c9e8bcddd64131b/raw/9c8bc58a99e2ea77d42abd41376e5e1becabea69/movies.json";
      axios.get(MOVIE_URL)
      .then((response) => {
        this.movies = response.data;
        // console.log(response);
      });
    },
  },
  mounted: function () {
    this.getMovies();
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
