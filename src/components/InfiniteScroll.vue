<template>
  <div class="movie-card">
    <img :src="post.img" :alt="post.title">
    <div class="info-card">
      <h2>{{post.title}}</h2>
      <p>tag</p>
      <p>{{post.info}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'InfiniteScroll',
  props: {
    post: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .movie-card{
    width: 20%;
    height: 40%;
    box-shadow: 0px 0px 7px 0px rgba(0,0,0,0.75);
    img{
      width: 100%;
    }
    .info-card{
      padding: 1em;
    }
  }
</style>
