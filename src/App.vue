<template>
  <div id="app">
    <top-bar @searchQuery="searchThis"></top-bar>
    <main>
    <infinite-scroll v-for="(post, ind) in posts" :key="ind" :post="post"></infinite-scroll>
    </main>
    <footer>
    <loading v-if="isLoading"></loading>
    </footer>
  </div>
</template>

<script>
import InfiniteScroll from './components/InfiniteScroll.vue'
import TopBar from './components/TopBar.vue'
import Loading from './components/Loading.vue'
import reqLink from './apiLink'

export default {
  data() {
    return {
      isLoading: false,
      posts: [],
      search: ''
    }
  },
  name: 'app',
  components: {
    TopBar,
    InfiniteScroll,
    Loading
  },
  methods: {
    getData: function() {
      this.isLoading = true
      fetch(reqLink)
        .then(res => res.json())
        .then(res => {
          (this.search === ''
            ? this.posts = this.posts.concat(res.posts)
            : this.posts = this.posts.concat(res.posts).filter(query => query.title.match(this.quer)))
        }
        )
        .finally(this.isLoading = false)
    },
    scrollControl: function(e) {
      if ((window.innerHeight + Math.ceil(window.scrollY)) >= e.target.body.offsetHeight) {
        this.getData()
        this.isLoading = true
      }
    },
    searchThis(text) {
      this.search = text
      this.getData()
    }
  },
  mounted() {
    this.getData()
    window.addEventListener('scroll', this.scrollControl)
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0 4rem;
}

#app {
  padding: 1rem;
}

main{
  display: flex;
  //flex-direction: column;
  flex-wrap:  wrap;
  justify-content: space-around;
  }

</style>
