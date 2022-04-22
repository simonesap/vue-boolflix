<template>
  <div id="app">
    
      <form action="" class="">
           <input type="text" class="form-control" 
                  v-model.trim="searchText"> 
           <button type="submit" 
                   class="btn btn-primary"
                   @click.prevent="$emit( 'search', searchText )">
                   Search
            </button>
       </form>

  </div>
</template>

<script>


export default {
  name: 'HeaderComp',

    data() {
        return {
            searchText: '',
        }
    },

  components: {
   
  }
}
</script>

<style lang="scss">
@import '../assets/style/general.scss';

</style>
