<template>
  <header>
    <div class="row justify-content-between me-0">
      <div class="col-2">
        <img class="logo" alt="Vue logo" src="@/assets/logo.png">
      </div>
      <div class="col-4 d-flex text-center justify-content-end  ">
        <img class="h_60 pt-4 me-3" src="https://noirflix.netlify.app/imgs/icon1.png" alt="">
        <input class="col-4 my-4 ms-2 rounded-2 p-1" type="text" placeholder="Cerca" @keyup.enter="resetInput" v-model="inputUtente"/>
        <button class="col-2 my-4 ms-2 rounded-2 bg-danger text-light" @click="resetInput">Cerca</button>
      </div>

    </div>

  </header>
</template>

<script>
export default {
  name: 'HeaderBoolfix',
  data() {
    return{
    inputUtente:"",

    };

  },
  methods:{
    resetInput(){
       this.$emit('search', this.inputUtente),
        this.inputUtente = ''
    }
  }
}
</script>

<style scoped lang="scss">
header{
  background-color: black;
}
.logo{
  height: 70px;
  padding: 10px;
}
.h_60{
  height: 60px;

}
</style>
