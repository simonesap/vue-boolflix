<template>

  <div>

    <div class="text_center">

      <div v-if="seriesCall == status">
        
      </div>
      <div v-else>
        <h2 class="p_20 text_white">Series</h2>
      </div>

    </div>

    <div class="flexRowWrap">
      <CardsComp
        v-for="(element, index) in seriesCall"
        :key="index"
        :seriesCard="element" />
    </div>
  
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
            status: false,
        }
    },
}
</script>

<style lang="scss">
@import '../../assets/style/general.scss';

</style>
