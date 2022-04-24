<template>

  <div>
    
    <CardsComp
        :seriesCard="seriesCall"
    />

  </div>

</template>

<script>
import CardsComp from './CardsComp.vue';


export default {
  name: 'SeriesList',

  components: {
      CardsComp,
  },

  props: {
      seriesCall: Array,
  },

  data() {
        return {
            
        }
    },
}
</script>

<style lang="scss">
@import '../../assets/style/general.scss';

</style>
