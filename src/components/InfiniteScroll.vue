<template>
  <article class="movie-card font-default">
    <img class="movie-img" :src="post.img" :alt="post.title">
    <main class="info-card">
      <h2>{{post.title}}</h2>
      <p>{{post.tag}}</p>
      <p>{{post.info}}</p>
    </main>
    <footer>
      <div class="rating-stars">
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
      </div>
      <span class="facebook-rounded"> <i class="fab fa-facebook-f awesome-facebook"></i> </span>
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

<style lang="scss">

  .info-card, .movie-card > footer{
    border: solid #d3d2d6d0;
    border-width: 0 1px 1px;
    padding: 0 2rem;
    width: 100%;
  }

  .movie-card{
    display: flex;
    flex-flow: column;
    //padding-bottom: 1rem;
    background-color: #fefefe;
    box-shadow: 0px 2px 5px -2px rgba(50,40,100,0.75);
    border-radius: .2rem;
    width: calc(25% - 1rem);
    //flex-basis: calc(25% - 1rem) ;
    overflow: hidden;
    .movie-img{
      width: 100%;
      display: block;
    }
    footer{
      display: flex;
      justify-content: space-between;
      padding-bottom: 1rem;
      padding-top: 1rem;
      .awesome-facebook{
        color: #fefefe
      }
    }
    .info-card{
      display: flex;
      flex-flow: column;
    }
  }

  .info-card{
    .font-default{
      font-size: 12px;
    }
  }
  .awesome-facebook{
    text-align: center;
    width: 1.4rem;
    height: 1.4rem;
    background-color: rgb(199, 199, 199);
    border-radius: 100%;
    padding-right: .1rem;
    padding-top: .2rem
  }
  }
</style>
