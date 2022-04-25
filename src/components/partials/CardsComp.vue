<template>

    <div>

        <div v-if="!filmCard == status"
            class="flexRowWrap container-default-2">
            <h2 class="d_none p_20"
                v-if="(!filmCard == status) ? 'd_flex' : '' ">
                Film
            </h2>
        
            <div
                class="p-20 flexColWrap fs_2 text_uppercase bg-custom-black text_white"
                v-for="(element, index) in filmCard"
                :key="index">   
                
                <img id="image" :src="`https://image.tmdb.org/t/p/original${element.poster_path}`" :alt="`Film-picture: ${element.title}`">
                <div v-if="element.original_language === 'it'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/it.png" alt="">
                </div>
                <div v-else-if="element.original_language === 'en-US'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/us.png" alt="">
                </div>
                <div v-else-if="element.original_language === 'en'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/gb.png" alt="">
                </div> 
                <div v-else-if="element.original_language === 'de'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/de.png" alt="">
                </div> 
                <div v-else-if="element.original_language === 'fr'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/mf.png" alt="">
                </div> 
                <div v-else-if="element.original_language === 'es'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/es.png" alt="">
                </div> 
                <div v-else class="flexCenter p_10">
                    <h5>Flag Undefined</h5>
                </div> 
                <div class="p_10"><span>Titolo: </span>{{element.title}}</div>
                <div class="p_10"><span>Titolo originale: </span>{{element.original_title}}</div>
                <div class="p_10"><span>Lingua originale: </span>{{element.original_language}}</div>
                <div class="p_10"><span>Media dei voti: </span>{{element.vote_average}}</div>
                <div v-if="!element.overview == '' ">
                    <div id="overview" class="p_10"><span>Overview: </span>{{element.overview}}</div>
                </div>
                <div v-else>
                    <div id="overview" class="p_10"><span>Overview: </span>Undefined</div>
                </div>
            </div>
        </div>

        <div v-else class="flexRowWrap container-default-2">
            <h2 class="p_20">Series</h2>
            <div
                class="p-20 flexColWrap fs_2 text_uppercase bg-custom-black text_white"
                v-for="(element, index) in seriesCard"
                :key="index">   
                
                <img id="image" :src="`https://image.tmdb.org/t/p/original${element.poster_path}`" :alt="`Film-picture: ${element.title}`">
                <div v-if="element.original_language === 'it'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/it.png" alt="">
                </div>
                <div v-else-if="element.original_language === 'en-US'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/us.png" alt="">
                </div>
                <div v-else-if="element.original_language === 'en'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/gb.png" alt="">
                </div> 
                <div v-else-if="element.original_language === 'de'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/de.png" alt="">
                </div> 
                <div v-else-if="element.original_language === 'fr'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/mf.png" alt="">
                </div> 
                <div v-else-if="element.original_language === 'es'" class="flexCenter p_10">
                    <img src="https://flagcdn.com/28x21/es.png" alt="">
                </div> 
                <div v-else class="flexCenter p_10">
                    <h5>Flag Undefined</h5>
                </div> 
                <div class="p_10"><span>Titolo: </span>{{element.name}}</div>
                <div class="p_10"><span>Titolo originale: </span>{{element.original_name}}</div>
                <div class="p_10"><span>Lingua originale: </span>{{element.original_language}}</div>
                <div class="p_10"><span>Media dei voti: </span>{{element.vote_average}}</div>
                <div v-if="!element.overview == '' ">
                    <div id="overview" class="p_10"><span>Overview: </span>{{element.overview}}</div>
                </div>
                <div v-else>
                    <div id="overview" class="p_10"><span>Overview: </span>Undefined</div>
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
      filmCard: Array,
      seriesCard: Array,
  },

  data() {
        return {
            status: false,
            flags: [
                {
                    it: 'https://flagcdn.com/16x12/it.png',
                    us: 'https://flagcdn.com/16x12/us.png',
                    uk: 'https://flagcdn.com/16x12/gb.png',
                }
            ]
        }
    },

    computed: {
        
    },

    methods: {

        getMovieFlags() {
           
                this.filmCard.forEach( ( element ) => {
                    if ( element.original_language === 'it' ) {
                        return this.flags.it
                    }
                    else if ( element.original_language === 'us' ) {
                        return this.flags.us
                    }
                    else if ( element.original_language === 'uk' ) {
                        return this.flags.uk
                     }
                     else {
                        return 'Flag Undefind'
                    }
                }) 
            }
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/general.scss';

    span {
        color: red;
    }

    #image {
        width: 350px;
        height: 400px;
    }

    #overview {
        width: 350px;
    }

</style>
