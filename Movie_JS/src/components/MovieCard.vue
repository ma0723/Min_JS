<template>
  <div>
    <div class="col mb-4">
      <div class="card">
        <img :src="'https://image.tmdb.org/t/p/w500/' + poster_path" alt="">
        <div class="card-body">
          <h5 class="card-title">{{ title }}</h5>
          <p class="card-text">{{ overview }}</p>
        </div>
      </div>
    </div>

    <!-- <p>title: {{ title }}</p> -->
    <!-- <img :src="'https://image.tmdb.org/t/p/w500/' + poster_path" alt=""> -->
    <!-- <p>overview: {{ overview }}</p> -->
  </div>
</template>

<script>
export default {
  name: 'MovieCard',
  props: {
    title: {
      type: String,
      required: true
    },
    poster_path: {
      type: String,
      required: true
    },
    overview: {
      type: String,
      required: true
    },
  }
}

</script>

<style>

</style>