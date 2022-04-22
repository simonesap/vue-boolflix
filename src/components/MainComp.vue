<template>
  <div>

      <FilmsList
        :filmCall="libraryCall"
      />

      <SeriesList/>

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
        libraryCall: Object,
    }

}
</script>

<style lang="scss">
@import '../assets/style/general.scss';

</style>
