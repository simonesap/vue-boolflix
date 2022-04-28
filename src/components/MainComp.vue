<template>
  <div>

    <h2 class="text_uppercase text_white container-default-2 p_10">originali boolflix</h2>
      <FilmsList
        :filmCall="libraryCallMovies"
        :personCall="libraryCallPerson"
      />

      <SeriesList
        :seriesCall="libraryCallSeries"
        :personCall="libraryCallPerson"
      />

      <div>
        <SlickComp/>
      </div>

  </div>
</template>

<script>
import FilmsList from './partials/FilmsList.vue'
import SeriesList from './partials/SeriesList.vue'
import SlickComp from './SlickComp.vue'


export default {
  name: 'MainComp',

  components: {
      FilmsList,
      SeriesList,
      SlickComp,
  },

    props: {
        libraryCallMovies: Array,
        libraryCallSeries: Array,
        libraryCallPerson: Array,
    }

}
</script>

<style lang="scss">
@import '../assets/style/general.scss';

    body {
        background: $gray-medium;
    }

</style>
