<template>
<main class="container-fluid">
    <div class="row gap-2 flex-wrap text-light justify-content-center">
        <div class="col-5 fs-3 border border-2 mt-2" v-for="item in films" :key="item.id">
            <p>TITOLO: {{item.title}}</p>
            <p>TITOLO ORIGINALE: {{ item.original_title }}</p>
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
