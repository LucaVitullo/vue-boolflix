<template>
<main class="container-fluid">
    <div class="row flex-wrap text-light justify-content-evenly">
        <h1 class="bg-dark text-center mb-0 p-2 border-light border-bottom">FILM</h1>
        <div class="col-2 fs-4 border border-2 m-2" v-for="item in films" :key="item.id">
            <p class="fs-6">TITOLO: {{item.title}}</p>
            <p class="fs-6">TITOLO ORIGINALE: {{ item.original_title }}</p>
            <img :src="showFlags (item.original_language)">
            <p class="fs-6">VOTO: {{ item.vote_average }}</p>
        </div>
        <h1 class="bg-dark text-center border-light border-bottom">SERIE</h1>
        <div class="col-2 fs-4 border border-2 m-2" v-for="item in series" :key="item.id">
            <p class="fs-6">TITOLO: {{item.name}}</p>
            <p class="fs-6">TITOLO ORIGINALE: {{ item.original_name }}</p>
            <img :src="showFlags (item.original_language)">
            <p class="fs-6">VOTO: {{ item.vote_average }}</p>
        </div>
    </div>
</main>

</template>

<script>

export default {
    name:"MainBoolfix",
    props:{
        films: Array,
        series:Array,
    },
    methods:{
        showFlags(flag){
            if( flag === "ja"){
                return "https://www.kidlink.org/icons/f0-jp.gif";
            }else if ( flag === "en"){
                return "https://www.kidlink.org/icons/f0-gb.gif";
            }
            return `https://www.kidlink.org/icons/f0-${flag}.gif`;

        },

    }
};
</script>

<style lang='scss' scoped>
.col-2{
    background-color: rgba($color: #9e9e9e, $alpha: 0.3);
}

</style>
