<template>
  <div>
    
    <HeaderComp
      @search="searching"
    />
    
    <MainComp/>

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
      InputSearch: '',
      api_key: '72f00d1d6ae3b6f495d244fb43ac83ce&query',
      library: [],
    }
  },

  created() {
    axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.api_key}&query=${this.InputSearch}&region=it-IT`)
      .then( (res) => {
        console.log(res);
        this.library = res;
        console.log(this.library)
      })
      .catch( (error) => {
          console.log( error )
      })
  },

  computed: {

  },

  methods: {

    searching( element ) {
      this.InputSearch = element;
      return
    }
  },

}
</script>

<style lang="scss">
@import './assets/style/general.scss';
@import url('https://fonts.googleapis.com/css2?family=Fira+Sans+Extra+Condensed&display=swap');

</style>
