<template>

  <div class="container-default-2">
    
    <!-- <VueSlickCarousel :arrows="true" :dots="true">
      <div class="d_flex justify_center">
        <div class="" v-for="(element,index) in libraryImg"  :class="element <= methodFunction(i) ? '`${element.poster_path}`' : '' " :key="index">
            <div class="flexRowWrap" v-for="i in 5" :key="i">
                <img id="image" :src="`https://image.tmdb.org/t/p/w342/${element.poster_path}`" 
                 :alt="`Film-picture: ${libraryImg.title}`" class="image">
                 <img id="image" :src="`https://image.tmdb.org/t/p/w342/${element.poster_path}`" 
                 :alt="`Film-picture: ${libraryImg.title}`" class="image">
                 <img id="image" :src="`https://image.tmdb.org/t/p/w342/${element.poster_path}`" 
                 :alt="`Film-picture: ${libraryImg.title}`" class="image">
                 <img id="image" :src="`https://image.tmdb.org/t/p/w342/${element.poster_path}`" 
                 :alt="`Film-picture: ${libraryImg.title}`" class="image">
            </div>
            
        </div>
      </div>
      <div class="d_flex justify_center">2ciao</div>
      <div class="d_flex justify_center">3ciao</div>
      <div class="d_flex justify_center">ciao</div>
    </VueSlickCarousel> -->

  </div>

</template>

<script>
//  import VueSlickCarousel from 'vue-slick-carousel'
//  import axios from 'axios';


export default {
  name: 'SlickComp',

    data() {
        return {
            slickOptions: {
                slidesToShow: 3,
            },
            api_key: '72f00d1d6ae3b6f495d244fb43ac83ce',
            libraryImg: [],
    }
    },

    components: {
        // VueSlickCarousel,
  },

  created() {
      // this.callApiMoviesImage(  )
  },

  methods: {
    //   callApiMoviesImage(  ) {
    //   axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.api_key}&query=movie&poster_path&region=it-IT`)
    //   .then( (res) => {
    //     console.log(res);
    //     this.libraryImg = res.data.results;
    //     console.log('Movies',this.libraryImg)
    //   })
    //   .catch( (error) => {
    //       console.log( error )
    //   })
    // },
    // methodFunction(i) {
    //     for(i = 0; i <= 5; i++) {
    //         return
    //     }
    // }
  }
}
</script>

<style lang="scss">
@import 'vue-slick-carousel/dist/vue-slick-carousel.css';
  // optional style for arrows & dots
@import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css';
@import '../assets/style/general.scss';

    .image {
        width: 25%;
        height: 25%;
    }

</style>
