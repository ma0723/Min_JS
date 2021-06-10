<template>
  <div class="home">
    <div class="row row-cols-1 row-cols-md-5 g-4">
      <MovieCard 
        v-for="(movie, idx) in movies" 
        :key="idx" 
        :title="movie.title"
        :poster_path="movie.poster_path"
        :overview="movie.overview"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import MovieCard from "@/components/MovieCard.vue";

export default {
  name: "Home",
  components: {
    MovieCard,
  },
  data: function () {
    return {
      movies: this.$route.query.movies
    }
  }
};
</script>
