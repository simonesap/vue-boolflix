<template>

  <div>
    
    <CardsComp/>

  </div>

</template>

<script>
import CardsComp from './CardsComp.vue'


export default {
  name: 'FilmsList',

  components: {
    CardsComp,
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
