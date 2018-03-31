<template>
  <article class="movie-card">
    <img :src="post.img" :alt="post.title">
    <main class="info-card">
      <h2>{{post.title}}</h2>
      <p class="font-default">tag</p>
      <p class="font-default">{{post.info}}</p>
    </main>
    <footer>
        <span class='fa fa-star'></span>
        <span class='fa fa-star'></span>
        <span class='fa fa-star'></span>
        <span class='fa fa-star'></span>
        <span class='fa fa-star'></span>
    </footer>
</article>

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
    width: 100%;
    box-shadow: 0px 2px 5px -2px rgba(50,40,100,0.75);
    border-radius: .2rem;
    overflow: hidden;
    img{
      width: 100%;
    }
    .info-card{
      display: flex;
      flex-flow: column;
      padding: 2rem;
      width: 90%;

    }
  }

  .info-card{
    .font-default{
      font-size: 12px;
    }
  }
</style>
