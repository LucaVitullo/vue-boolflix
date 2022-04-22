<template>
  <header>
    <div class="row justify-content-between me-0">
      <div class="col-6">
        <img alt="Vue logo" src="@/assets/logo.png">
      </div>
      <div class="col-6 d-flex text-center justify-content-end p-4 ">
        <input class="col-4 me-2 rounded-2 p-1" type="text" placeholder="Cerca" @keyup.enter="resetInput" v-model="inputUtente"/>
        <button class="col-2 rounded-2 bg-danger text-light" @click="resetInput">Cerca</button>
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
header img{
  height: 70px;
  padding: 10px;
}
</style>
