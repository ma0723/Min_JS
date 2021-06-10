<template>
  <div>
    <button @click="randomMovie">PICK</button>
    <p>{{ movie.title }}</p>
  </div>
</template>

<script>
import _ from 'lodash'
export default {
  name: "Random",
  data: function () {
    return {
      movies: this.$route.query.movies,
      movie: {}
    }
  },
  methods: {
    randomMovie: function () {
      this.movie = _.sample(this.movies)
    }
  }
};
</script>

<style>
</style>