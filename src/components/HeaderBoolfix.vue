<template>
  <div class="hello">
    <img class="h-50" alt="Vue logo" src="@/assets/logo.png">

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello img{
  height: 80px;
}
</style>
