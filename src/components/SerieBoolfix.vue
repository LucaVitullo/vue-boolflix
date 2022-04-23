<template>
    <div class="row justify-content-center me-0 gap-2 text-light">
        <div class="col-3 bg_lv fs-4 p-1 border border-2 m-2" v-for="item in series" :key="item.id">
                <img class=" image" :src="`http://image.tmdb.org/t/p/original${item.poster_path}`"
                 @error="imageNotFound"
                 alt=""
                 > 
            <div class="overlay">
                <div class="text fs_10 ">
                    <p class="fs_10 m-1">TITOLO: {{item.name}}</p>
                    <p class="fs_10 m-1">TITOLO ORIGINALE: {{ item.original_name }}</p>
                    <div class="container-flag  d-flex justify-content-center">
                        <img class="flag d-block" :src="showFlags (item.original_language)" 
                         @error="imageNotFound"
                        >
                    </div>
                    <div class="fs_10 d-inline-block" v-for="(n, index) in 5" :key="index">
                        <font-awesome-icon
                            :class="n <= item.vote_average / 2 ? 'text-warning' : ''"
                            :icon="
                            item.vote_average / 2 == 0
                            ? 'fa-regular fa-star'
                            : 'fa-solid fa-star'
                            "
                        />
                    </div>
                    <p class="fs_10 m-100 w-100">DESCRIZIONE:  {{item.overview}}</p>

                </div>
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

.col-3 {
  position: relative;
}

.image {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  opacity: 0;
  transition: .5s ease;
  background-color: black;
}

.col-3:hover .overlay {
  opacity: 1;
}

.text {
  color: white;
  width: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}


.bg_lv{
    background-color: rgba($color: #9e9e9e, $alpha: 0.3);
    cursor: pointer;

};
.flag{
    width: 20px

};
.fs_10{
    font-size: 10px;
}
</style>