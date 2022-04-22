<template>

  <div class="bg-custom-black">
    
    <div class="container-default-2 flexBetween">

        <div class="">
          <h2 class="text_uppercase  text_red fs_8">boolflix</h2> 
      </div>

      <form action="" class="p_10">
           <input type="text" class="form-control" 
                  v-model.trim="searchText"> 
           <button type="submit" 
                   class="btn btn-primary"
                   @click.prevent="$emit( 'search', searchText )"
                   v-on:keyup.enter="submit"
                   >
                   Search film...
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
