<template>

  <div>
    
    <CardsComp
        :filmCard="filmCall"
    />

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
      filmCall: Object,
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
