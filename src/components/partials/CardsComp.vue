<template>
    <div>
        <div v-if="!filmCard == status" id="card" class="fs_2 text_uppercase text_white">

            <div v-show="active" @mouseover="active = false" >
                <img @mouseover="activeHover = true"  
                    id="image" :src="`https://image.tmdb.org/t/p/original/${filmCard.poster_path}`" 
                    :alt="`Film-picture: ${filmCard.title}`">
            </div>
            <div v-show="activeHover" id="info" class="bg-custom-black">
                <div @mouseleave="active = true" class="">
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

        <div v-else>
            <div v-if="active" @mouseover="active = false" id="info">
                <img @mouseover="activeHover = true" id="image" 
                    :src="`https://image.tmdb.org/t/p/original${seriesCard.poster_path}`" 
                    :alt="`Film-picture: ${seriesCard.title}`">
            </div>
            <div v-if="activeHover" id="info" class="bg-custom-black">
                <div @mouseleave="active = true" class="">
                    <div class="p-20 flexColWrap fs_2 text_uppercase bg-custom-black text_white">   
                        
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
            active: true,
            activeHover: false,
            status: false,
            counter: 0,
            // flags: [
            //     {
            //         it: 'https://flagcdn.com/16x12/it.png',
            //         us: 'https://flagcdn.com/16x12/us.png',
            //         uk: 'https://flagcdn.com/16x12/gb.png',
            //     }
            // ],
        }
    },

    computed: {
    
    },

    methods: {

        getStar(element) {
            
            return Math.ceil(element.vote_average) / 2;
           
        },
        // getMovieFlags() {
           
        //         this.filmCard.forEach( ( element ) => {
        //             if ( element.original_language === 'it' ) {
        //                 return this.flags.it
        //             }
        //             else if ( element.original_language === 'us' ) {
        //                 return this.flags.us
        //             }
        //             else if ( element.original_language === 'uk' ) {
        //                 return this.flags.uk
        //              }
        //              else {
        //                 return 'Flag Undefind'
        //             }
        //         }) 
        //     },
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
        height: 150px;
        overflow: auto;
    }

    #card {
        width: 350px;
        height: 400px;
    }

    #info {
        width: 350px;
        height: 400px;
    }

</style>
