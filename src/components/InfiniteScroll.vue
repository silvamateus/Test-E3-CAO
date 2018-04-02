<template>
  <article class="movie-card">
    <img :src="post.img" :alt="post.title">
    <main class="info-card">
      <h2>{{post.title}}</h2>
      <p class="font-default">tag</p>
      <p class="font-default">{{post.info}}</p>
    </main>
    <footer>
      <div class="rating-stars">
        <i class='fa fa-star'></i>
        <i class='fa fa-star'></i>
        <i class='fa fa-star'></i>
        <i class='fa fa-star'></i>
        <i class='fa fa-star'></i>
      </div>
      <span class="facebook-rounded"> <i class="fa fa-facebook awesome-facebook"></i> </span>
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
      .awesome-facebook{
        color: #fefefe
    }
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
  .awesome-facebook{
    text-align: center;
    width: 1.1rem;
    background-color: rgb(199, 199, 199);
    border-radius: 100%;
    padding-top: .3rem;
    padding-right: .4rem;
    padding-left: .2rem
  }
</style>
