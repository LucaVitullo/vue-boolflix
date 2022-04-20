<template>
  <header>
    <div class="row justify-content-between">
      <div class="col-6">
        <img alt="Vue logo" src="@/assets/logo.png">
      </div>
      <div class="col-6 d-flex text-center justify-content-end p-4 me-0">
        <input class="col-4 me-2" type="text" placeholder="Cerca" @keyup.enter="$emit('search', inputUtente)" v-model="inputUtente"/>
        <button class="col-2" @click="$emit('search', inputUtente)">Cerca</button>
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
