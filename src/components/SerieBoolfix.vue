<template>
    <div class="row justify-content-center me-0 gap-2 text-light">
        <div class="col-2 bg_lv fs-4 p-1 border border-2 m-2" v-for="item in series" :key="item.id" >
            <img class="w-100" :src="`http://image.tmdb.org/t/p/original${item.poster_path}`"
             @error="imageNotFound"
             alt="">
            <p class="fs-6">TITOLO: {{item.name}}</p>
            <p class="fs-6">TITOLO ORIGINALE: {{ item.original_name }}</p>
            <img class="flag d-block" :src="showFlags (item.original_language)"
                @error="imageNotFound"
            >
            <div class="fs-6 d-inline-block" v-for="(n, index) in 5" :key="index">
                <font-awesome-icon
                 :class="n <= item.vote_average / 2 ? 'text-warning' : ''"
                 :icon="
                    item.vote_average / 2 == 0
                  ? 'fa-regular fa-star'
                  : 'fa-solid fa-star'
                 "
                />
            </div>
        </div>  
    </div>
</template>

<script>
export default{
    name:"SerieBoolfix",
    props:{
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

        imageNotFound(error){
            error.target.src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ8uia93jUhtlaNB5s9-xnmhh8tek0NsQ0BMg&usqp=CAU"
        },

    }

}
</script>

<style lang='scss' scoped>
.bg_lv{
    background-color: rgba($color: #9e9e9e, $alpha: 0.3);
    cursor: pointer;

};
.flag{
    width: 20px

};
</style>