<template>

  <div>
    
    <div
        v-for="(element, index) in filmCard"
        :key="index"
    >
        <span>{{element.title}}</span>
        <span>{{element.original_title}}</span>
        <span>{{element.original_language}}</span>
        <span>{{element.vote_average}}</span>
    </div>
 

  </div>

</template>

<script>



export default {
  name: 'CardsComp',

  components: {
  
  },

  props: {
      filmCard: Object,
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
