<template>
  <div id="app">
    <HeaderBoolfix @search="queryApi" />
    <MainBoolfix :films="films" :series="series"/>
  </div>
</template>

<script>
import HeaderBoolfix from './components/HeaderBoolfix.vue';
import MainBoolfix from './components/MainBoolfix.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderBoolfix,
    MainBoolfix,
  },
  data(){
    return{
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '6a9fd3900bf469fa4eda0085bd9879cf',
      inputUtente:'',
      films:[],
      series:[],
    }
  },
  methods:{
    queryApi(inputUtente){
      const params = {
        query: inputUtente,
        api_key: this.apiKey,
        language: 'it-IT',

      }
      axios.get(this.apiUrl + 'movie', {params}).then((response)=>{
        console.log(response.data.results)
        this.films = response.data.results
      })
      axios.get(this.apiUrl + 'tv', {params}).then((response)=>{
        console.log(response.data.results)
        this.series = response.data.results
      })
    }

  }
}
</script>

<style lang="scss">
@import'@/assets/style/general.scss';

</style>
