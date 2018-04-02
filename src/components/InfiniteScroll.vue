<template>
  <article class="movie-card font-default">
    <img :src="post.img" :alt="post.title">
    <main class="info-card">
      <h2>{{post.title}}</h2>
      <p>tag</p>
      <p>{{post.info}}</p>
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

  .info-card, footer{
    border: solid #d3d2d6d0;
    border-width: 0 1px 1px;
    padding: 0 2rem;
    width: 100%;
  }

  .movie-card{
    width: 100%;
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    box-shadow: 0px 2px 5px -2px rgba(50,40,100,0.75);
    border-radius: .2rem;
    overflow: hidden;
    img{
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
      //display: flex;
      //flex-flow: column;
      text-overflow: ellipsis;
      word-wrap: break-word;
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
