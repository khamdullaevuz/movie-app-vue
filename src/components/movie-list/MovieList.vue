<template>
  <ul class="movie-list list-group">
    <MovieListItem v-for="movie in movies" :movie="movie" />
  </ul>
</template>

<script>
import MovieListItem from "../movie-list-item/MovieListItem.Vue";
export default {
  components: {
    MovieListItem,
  },
  data() {
    return {
      movies: [
        {
          name: "Omar",
          viewers: 811,
          favourite: false,
          like: true,
        },
        {
          name: "Empire of osman",
          viewers: 411,
          favourite: false,
          like: false,
        },
        {
          name: "Ertugrul",
          viewers: 711,
          favourite: true,
          like: false,
        },
      ],
    };
  },
};
</script>

<style scoped>
.movie-list {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
