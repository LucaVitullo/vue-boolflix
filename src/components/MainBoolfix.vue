<template>
<main class="container">
    <div class="row h-50 pt-3 gap-2 flex-wrap">
        <div class=" border" v-for="item in films" :key="item.id">
            <p>titolo:{{item.name}}</p>
            <p>titolo originale: {{ item.original_name }}</p>
            <p>lingua: {{ item.original_language }}</p>
            <p>voto: {{ item.vote_average }}</p>

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

</style>
