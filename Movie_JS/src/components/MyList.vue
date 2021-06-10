<template>
  <div>{{ myMovie }}</div>
</template>

<script>
export default {
  name: "MyList",
  props: {
    // movie: {
    //   type: Object,
    //   required: true
    // },
    myMovie: {
      type: String,
      required: true
    }
  },

}
</script>

<style>

</style>