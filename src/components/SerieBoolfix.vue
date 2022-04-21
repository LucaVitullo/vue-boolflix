<template>
    <div class="row justify-content-center gap-3 text-light">
        <div class="col-2 fs-4 p-1 border border-2 m-2" v-for="item in series" :key="item.id" >
            <img class="w-100" :src="`http://image.tmdb.org/t/p/original${item.poster_path}`"
             @error="imageNotFound"
             alt="">
            <p class="fs-6">TITOLO: {{item.name}}</p>
            <p class="fs-6">TITOLO ORIGINALE: {{ item.original_name }}</p>
            <img class="flag" :src="showFlags (item.original_language)"
                @error="imageNotFound"
            >
            <p class="fs-6">VOTO: <font-awesome-icon icon="fa-solid fa-star" class="text-warning"/> {{ item.vote_average }}</p>
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
.col-2{
    background-color: rgba($color: #9e9e9e, $alpha: 0.3);
};
.flag{
    width: 20px

};