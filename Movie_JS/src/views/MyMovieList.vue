<template>
  <div>
    <MyListForm @my-movie="onMyMovie"/>
      <!-- v-for="(movie, idx) in movies" 
      :key="idx"
      :movie="movie" -->
    <MyList 
      v-for="(myMovie, idx) in myMovies"
      :key="idx"
      :myMovie="myMovie"
    />
  </div>
</template>

<script>
import MyListForm from "@/components/MyListForm.vue";
import MyList from "@/components/MyList.vue";
export default {
  name: "MyMovieList",
  components: {
    MyListForm,
    MyList,
  },
  data: function () {
    return {
      movies: this.$route.query.movies,
      myMovies: []
    }
  },
  methods: {
    onMyMovie: function (myMovie) {
      this.myMovies.push(myMovie)
    },

  }
};
</script>

<style>
</style>