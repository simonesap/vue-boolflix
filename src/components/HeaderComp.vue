<template>

  <div class="bg-custom-black">
    
    <div class="container-default-2 flexBetween">

        <div class="d_flex align_center">
          <h2 class="text_uppercase  text_red fs_8">boolflix</h2> 
          <div class="text_white p_20 ">
            <a class="text_white text_decoration p_10" href="#">Home</a>
            <a class="text_white text_decoration p_10" href="#">Serie Tv</a>
            <a class="text_white text_decoration p_10" href="#">Film</a>
            <a class="text_white text_decoration p_10" href="#">Originali</a>
            <a class="text_white text_decoration p_10" href="#">Aggiunti di recente</a>
            <a class="text_white text_decoration p_10" href="#">La mia lista</a>
          </div>
          
      </div>

      <form action="" class="p_10">
           <input type="text" class="form-control" 
                  v-model.trim="searchText"> 
           <button type="submit" 
                   class="btn btn-primary"
                   @click.prevent="$emit( 'search', searchText )"
                   v-on:keyup.enter="submit"
                   >
                   Search...
            </button>
       </form>

    </div>
      

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
