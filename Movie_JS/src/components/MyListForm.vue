<template>
  <div>
    <!-- :value="movieTitle" -->
    <input 
      type="text" 
      v-model="movieTitle"
      @keyup.enter="myMovie"
    >
    <button @click="myMovie">ADD</button>

  </div>
</template>

<script>
export default {
  name: "MyListForm",
  data: function () {
    return {
      movieTitle: ''
    }
  },
  methods: {
    myMovie: function () {
      this.$emit("my-movie", this.movieTitle)
      this.movieTitle = ""
    }
  }
}
</script>

<style>

</style>