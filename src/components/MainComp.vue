<template>
  <div>

      <FilmsList
        :filmCall="libraryCallMovies"
      />

      <SeriesList
        :seriesCall="libraryCallSeries"
      />

  </div>
</template>

<script>
import FilmsList from './partials/FilmsList.vue'
import SeriesList from './partials/SeriesList.vue'


export default {
  name: 'MainComp',

  components: {
      FilmsList,
      SeriesList,
  },

    props: {
        libraryCallMovies: Object,
    }

}
</script>

<style lang="scss">
@import '../assets/style/general.scss';

    body {
        background: $gray-medium;
    }

</style>
