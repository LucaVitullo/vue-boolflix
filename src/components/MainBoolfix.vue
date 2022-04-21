<template>
<main>
    <div class="container-fluid p-0">
        <h1 class="bg-dark text-center mb-0 p-2 border-light border-bottom text-danger">FILM</h1>
        <FilmBoolfix :films="films" />
        <h1 class="bg-dark text-center p-2  border-light border-bottom text-danger">SERIE</h1>
        <SerieBoolfix :series="series" />
    </div>

</main>

</template>

<script>
import FilmBoolfix from "./FilmBoolfix.vue";
import SerieBoolfix from "./SerieBoolfix.vue";

export default {
    name:"MainBoolfix",
    components:{
        FilmBoolfix,
        SerieBoolfix,
    },
    props:{
        films: Array,
        series:Array,
    },
};
</script>

<style lang='scss' scoped>


</style>
