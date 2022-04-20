<template>
  <div id="app">
    <HeaderBoolfix />
  </div>
</template>

<script>
import HeaderBoolfix from './components/HeaderBoolfix.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderBoolfix,
  },
  data(){
    return{
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '6a9fd3900bf469fa4eda0085bd9879cf'
    }
  },
  mounted(){

    const query = 'verde';
    const params = {
      query,
      api_key:this.apiKey,
      language: 'it-IT'
    }
    axios.get(this.apiUrl + 'tv', { params }).then((response)=>{
      console.log(response)
    }).catch(error=>{
      console.log(error);
    })

  }
}
</script>

<style lang="scss">
@import'@/assets/style/general.scss';

</style>
