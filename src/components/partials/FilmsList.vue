<template>

  <div>

    <div class="text_center">
      <div v-if="filmCall == status">
        
      </div>
      <div v-else>
        <h2 class="p_20 text_white">Film</h2>
      </div>
    </div>
    <div class="flexRowWrap">
      <CardsComp
      class="" 
      v-for="(element, index) in filmCall"
      :key="index" 
      :filmCard="element"
      :personCard="personCall"
      />
    </div>
  
  </div>

</template>

<script>
import CardsComp from './CardsComp.vue'


export default {
  name: 'FilmsList',

  components: {
    CardsComp,
  },

  props: {
      filmCall: Array,
      personCall: Array,
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
