<template>

  <div class="container-default flexRowWrap">
   
    <div
        class="p-20 flexColWrap fs_2 text_uppercase"
        v-for="(element, index) in filmCard"
        :key="index"
    >   
        <!-- <h2>Film</h2> -->
        <div class="p_10"><span>Titolo: </span>{{element.title}}</div>
        <div class="p_10"><span>Titolo originale: </span>{{element.original_title}}</div>
        <div class="p_10"><span>Lingua originale: </span>{{element.original_language}}</div>
        <div class="p_10"><span>Media dei voti: </span>{{element.vote_average}}</div>
    </div>

    <div
        class="p-20 flexColWrap fs_2 text_uppercase"
        v-for="(element, index) in seriesCard"
        :key="index"
    >   
        <!-- <h2>Series</h2> -->
        <div class="p_10"><span>Titolo: </span>{{element.title}}</div>
        <div class="p_10"><span>Titolo originale: </span>{{element.original_title}}</div>
        <div class="p_10"><span>Lingua originale: </span>{{element.original_language}}</div>
        <div class="p_10"><span>Media dei voti: </span>{{element.vote_average}}</div>
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
      seriesCard: Object,
  },

  data() {
        return {
            
        }
    },
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/general.scss';

    span {
        color: red;
    }

</style>
