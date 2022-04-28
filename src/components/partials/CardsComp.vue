<template>
    <div>
        <div v-if="!filmCard == status" class="card fs_2 text_uppercase text_white flip-card">

            <div class="flip-card-inner">
                 <!-- <div :style="{'background-image': `url(https://image.tmdb.org/t/p/w342/${filmCard.poster_path})`}"
                      class="image b_cover p_relative flip-card-front"> -->
                <div class="flip-card-front">
                    <img id="image" :src="`https://image.tmdb.org/t/p/original/${filmCard.poster_path}`" 
                         :alt="`Film-picture: ${filmCard.title}`" class="image">
                </div>
                <div class="info bg-custom-black flip-card-back">
                    <div v-if="filmCard.original_language === 'it'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/it.png" alt="">
                    </div>
                    <div v-else-if="filmCard.original_language === 'en-US'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/us.png" alt="">
                    </div>
                    <div v-else-if="filmCard.original_language === 'en'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/gb.png" alt="">
                    </div> 
                    <div v-else-if="filmCard.original_language === 'de'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/de.png" alt="">
                    </div> 
                    <div v-else-if="filmCard.original_language === 'fr'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/mf.png" alt="">
                    </div> 
                    <div v-else-if="filmCard.original_language === 'es'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/es.png" alt="">
                    </div> 
                    <div v-else class="flexCenter p_10">
                        <h5>Flag Undefined</h5>
                    </div> 
                    <div class="p_10"><span>Titolo: </span>{{filmCard.title}}</div>
                    <div class="p_10"><span>Titolo originale: </span>{{filmCard.original_title}}</div>
                    <div class="p_10"><span>Lingua originale: </span>{{filmCard.original_language}}</div>
                    <div class="p_10"><span>Data di uscita: </span>{{filmCard.release_date}}</div>
                    <div class="p_10"><span>Adulti: </span>{{filmCard.adult}}</div>
                    <div class="p_10" ><span>Attori: </span>{{nameList}}</div>
                    <div class="p_10">
                        <span>Media dei voti: </span>
                        <i v-for="i in 5" :key="i" :class="i <= getStar(filmCard) ? 'fas fa-star' : 'far fa-star'" class="text_gold"></i>
                    </div>
                    <div class="p_10">
                        
                    </div>
                    <div v-if="!filmCard.overview == '' ">
                        <div id="overview" class="p_10"><span>Overview: </span>{{filmCard.overview}}</div>
                    </div>
                    <div v-else>
                        <div id="overview" class="p_10"><span>Overview: </span>Undefined</div>
                    </div>
                </div>
            </div>
        </div>

        <div v-else class="card fs_2 text_uppercase text_white flip-card">

            <div class="flip-card-inner">
                <!-- <div :style="{'background-image': `url(https://image.tmdb.org/t/p/w342/${seriesCard.poster_path})`}"
                  class="image b_cover p_relative"> -->
                <div class="flip-card-front">
                    <img id="image" 
                         :src="`https://image.tmdb.org/t/p/original${seriesCard.poster_path}`" 
                         :alt="`Film-picture: ${seriesCard.title}`" class="image">
                </div>
                
                <div class="info bg-custom-black flip-card-back">  
                    <div v-if="seriesCard.original_language === 'it'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/it.png" alt="">
                    </div>
                    <div v-else-if="seriesCard.original_language === 'en-US'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/us.png" alt="">
                    </div>
                    <div v-else-if="seriesCard.original_language === 'en'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/gb.png" alt="">
                    </div> 
                    <div v-else-if="seriesCard.original_language === 'de'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/de.png" alt="">
                    </div> 
                    <div v-else-if="seriesCard.original_language === 'fr'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/mf.png" alt="">
                    </div> 
                    <div v-else-if="seriesCard.original_language === 'es'" class="flexCenter p_10">
                        <img src="https://flagcdn.com/28x21/es.png" alt="">
                    </div> 
                    <div v-else class="flexCenter p_10">
                        <h5>Flag Undefined</h5>
                    </div> 
                    <div class="p_10"><span>Titolo: </span>{{seriesCard.name}}</div>
                    <div class="p_10"><span>Titolo originale: </span>{{seriesCard.original_name}}</div>
                    <div class="p_10"><span>Lingua originale: </span>{{seriesCard.original_language}}</div>
                    <div class="p_10"><span>Data di uscita: </span>{{seriesCard.first_air_date}}</div>
                    <!-- <div class="p_10" v-for="(element,index) in personCard" :key="index"><span>Attori: </span>{{element.name}}</div> -->
                    <div class="p_10">
                        <span>Media dei voti: </span>
                        <i v-for="i in 5" :key="i" :class="i <= getStar(seriesCard) ? 'fas fa-star' : 'far fa-star'" class="text_gold"></i>
                    </div>
                    <div class="p_10">
                        
                    </div>
                    <div v-if="!seriesCard.overview == '' ">
                        <div id="overview" class="p_10"><span>Overview: </span>{{seriesCard.overview}}</div>
                    </div>
                    <div v-else>
                        <div id="overview" class="p_10"><span>Overview: </span>Undefined</div>
                    </div>
                </div>
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
      filmCard: Object,
      seriesCard: Object,
      personCard: Array,
  },

  data() {
        return {
            active: true,
            activeHover: false,
            status: false,
            filmsTitles: [],
            actorsMovies: [],
            nameList: [],
        }
    },

    computed: {
    
    },

    methods: {

        getStar(element) {
            
            return Math.ceil(element.vote_average) / 2;
           
        },

        moviesTitles() {
        this.filmCard.forEach( (el,i) => {
        return this.filmsTitles = el[i].title
            
        }) 
            console.log('Films title',this.filmsTitles)
        },
        
        actorsFilms() {
            this.personCard.forEach( (el,i) => {
                return this.actorsMovies = el[i].known_for[i].title
                
        }) 
            console.log('Actors Films',this.actorsMovies)
        },

        compareTitle() {
            if(this.filmsTitles == this.actorsMovies) {
                return this.personCard.filter( (res) => {
                    return this.nameList = res.name
                })
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/general.scss';

    span {
        color: red;
    }

    .b_cover {
        background-size: cover;
        background-position: center;
    }

    .image {
        width: 100%;
        height: 100%;
    }

    #overview {
        height: 150px;
        overflow: auto;
    }

    .card {
        width: 400px;
        height: 450px;
    }
    // .card:hover .info {
    //     display: block;
    // }

    .info {
        width: 100%;
        height: 100%;
    }

</style>
