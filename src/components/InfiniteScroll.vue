<template>
  <div class="info-card">
    <img src="https://lumiere-a.akamaihd.net/v1/images/image_b349f970.jpeg" alt="lol">
    <p></p>
  </div>
</template>

<script>
export default {
  name: 'InfiniteScroll',
  props: {
    msg: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .info-card{
    width: 80%;
    height: 60vh;
    box-shadow: 1px 0px 1px 0px #999;
    img{
      width: 100%;
    }
  }
</style>
