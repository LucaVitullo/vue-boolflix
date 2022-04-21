<template>
<main class="container-fluid">
    <div class="row gap-1 flex-wrap text-light justify-content-">
        <h1 class="bg-dark text-center">FILM</h1>
        <div class="col fs-4 border border-2 mt-2" v-for="item in films" :key="item.id">
            <p>TITOLO: {{item.title}}</p>
            <p>TITOLO ORIGINALE: {{ item.original_title }}</p>
            <p>LINGUA: {{ item.original_language }}</p>
            <p>VOTO: {{ item.vote_average }}</p>
        </div>
        <h1 class="bg-dark text-center">SERIE</h1>
        <div class="col fs-4 border border-2 mt-2" v-for="item in series" :key="item.id">
            <p>TITOLO: {{item.name}}</p>
            <p>TITOLO ORIGINALE: {{ item.original_name }}</p>
            <p>LINGUA: {{ item.original_language }}</p>
            <p>VOTO: {{ item.vote_average }}</p>
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
};
</script>

<style lang='scss' scoped>
main{
    background-image: url("https://assets.nflxext.com/ffe/siteui/vlv3/8459cea4-79ab-4f27-9ef0-a7c92a30a9bb/f4b0e424-f578-46d1-ac77-ba8f4763d581/IT-it-20220411-popsignuptwoweeks-perspective_alpha_website_large.jpg");
    background-size: contain;
    opacity: 0.9;
    background-position: center;
}

</style>
