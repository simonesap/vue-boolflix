<template>

    <div>

        <div v-if="!filmCard == status"
            class="flexRowWrap container-default-2">
            <h2 class="d_none p_20"
                v-if="d_flex">
                Film
            </h2>
        
            <div
                class="p-20 flexColWrap fs_2 text_uppercase"
                v-for="(element, index) in filmCard"
                :key="index">   
                
                <img :src="`https://image.tmdb.org/t/p/original${element.poster_path}`" :alt="`Film-picture: ${element.title}`">
                <div class="p_10"><span>Titolo: </span>{{element.title}}</div>
                <div class="p_10"><span>Titolo originale: </span>{{element.original_title}}</div>
                <div class="p_10"><span>Lingua originale: </span>{{element.original_language}}</div>
                <div class="p_10"><span>Media dei voti: </span>{{element.vote_average}}</div>
            </div>
        </div>

        <div v-else class="flexRowWrap container-default-2">
            <h2 class="p_20">Series</h2>
            <div
                class="p-20 flexColWrap fs_2 text_uppercase"
                v-for="(element, index) in seriesCard"
                :key="index">   
                
                <img :src="`https://image.tmdb.org/t/p/original${element.poster_path}`" :alt="`Film-picture: ${element.title}`">
                <div class="p_10"><span>Titolo: </span>{{element.name}}</div>
                <div class="p_10"><span>Titolo originale: </span>{{element.original_name}}</div>
                <div class="p_10"><span>Lingua originale: </span>{{element.original_language}}</div>
                <div class="p_10"><span>Media dei voti: </span>{{element.vote_average}}</div>
            </div>
        </div>
    </div>

</template>

<script>



export default {
  name: 'CardsComp',

  components: {
  
  },

  props: {
      filmCard: Array,
      seriesCard: Array,
  },

  data() {
        return {
            status: false,
        }
    },
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/general.scss';

    span {
        color: red;
    }

    img {
        width: 350px;
        height: 400px;
    }

</style>
