<template>
  <div>
    
    <HeaderComp
      @search="searching"
    />
    
    <MainComp
      :libraryCallMovies="libraryMovies"
      :libraryCallSeries="librarySeries"
      :libraryCallPerson="libraryPeople"
    />
   <!-- <div v-for="(element,index) in libraryPeople" :key="index">{{element.name}}</div> -->

  </div>
</template>

<script>
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',

  components: {
   HeaderComp,
   MainComp,
  },

  data() {
    return {
     
      api_key: '72f00d1d6ae3b6f495d244fb43ac83ce',
      libraryMovies: [],
      librarySeries: [],
      libraryPeople: [],
      actorsName: [],
      
      
      personNameActor: '',
      test: [],
      testDue: [],
    }
  },

  created() {
     
  },

  computed: {
    
  },

  methods: {

    searching( element ) {

      this.callApiMovies( element )
      
      this.callApiSeries( element )

      this.callApiPeople( element )

      this.nameActors( element )

      // this.actorsFilms( element )

      // this.moviesTitles( element )

      // this.compareActorsMovies( element )

      // this.actorsNamesCall(element)

      // this.callApiFlags( element )
      
    },

    callApiMovies( element ) {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.api_key}&query=${element}&year&adult&region=it-IT`)
      .then( (res) => {
        console.log(res);
        this.libraryMovies = res.data.results;
        console.log('Movies',this.libraryMovies)
      })
      .catch( (error) => {
          console.log( error )
      })
    },

    callApiSeries( element ) {
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${this.api_key}&query=${element}&first_air_date&region=it-IT`)
      .then( (res) => {
        console.log(res);
        this.librarySeries = res.data.results;
        console.log('Series',this.librarySeries)
      })
      .catch( (error) => {
          console.log( error )
      })
    },

    callApiPeople( element) {
      axios.get(`https://api.themoviedb.org/3/search/person?api_key=${this.api_key}&query=${element}&region=it-IT`)
      .then( (res) => {
        console.log(res);
        this.libraryPeople = res.data.results;
        console.log('Person',this.libraryPeople)
        
    })
    .catch( (error) => {
        console.log( error )
    })

   },

   nameActors() {
      
      this.libraryPeople.forEach( (el,i) => {
        return this.actorsName = el[i].name
        
      }) 
        console.log('Actors',this.actorsName)
    },

    // actorsNamesCall(element) {
     
    //  for(element in this.libraryPeople) {
    //    return this.testDue = element.name
    //  }
      
    // },

    // compareActorsMovies( element,el ) {
    
    // for (element in this.libraryPeople & el in this.libraryMovies) {
    //   if(element.title.includes(el.known_for.title)) {
    //     return this.test = el.name
    //   }
     
    // } console.log('AAAAAAAAABBBBBBB',this.test)
     
    // }

    // callApiFlags( ) {
    //   axios.get('https://flagcdn.com/16x12/.png')
    //   .then( ( res ) => {
    //     console.log( res )
    //     this.libraryFlags = res
    //   })
  }

}
</script>

<style lang="scss">
@import './assets/style/general.scss';
@import url('https://fonts.googleapis.com/css2?family=Fira+Sans+Extra+Condensed&display=swap');

  body {
    font-family: 'Fira Sans Extra Condensed', sans-serif;
  }

</style>
