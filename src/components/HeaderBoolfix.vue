<template>
  <header>
    <img alt="Vue logo" src="@/assets/logo.png">

  </header>
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
header{
  background-color: black;
}
header img{
  height: 70px;
  padding: 10px;
}
</style>
