<template>
  <div>

      <FilmsList/>

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
  }
}
</script>

<style lang="scss">
@import '../assets/style/general.scss';

</style>
