<template>
  <div id="app">
    <infinite-scroll v-for="(post, ind) in posts" :key="ind" :post="post"></infinite-scroll>
    <loading v-if="isLoading"></loading>
  </div>
</template>

<script>
import InfiniteScroll from './components/InfiniteScroll.vue'
import Loading from './components/Loading.vue'
import reqLink from './apiLink'

export default {
  data() {
    return {
      isLoading: false,
      posts: []
    }
  },
  name: 'app',
  components: {
    InfiniteScroll,
    Loading
  },
  methods: {
    getData: function() {
      this.isLoading = true
      fetch(reqLink)
        .then(res => res.json())
        .then(res => (this.posts = this.posts.concat(res.posts)))
        .finally(this.isLoading = false)
    }
  },
  mounted() {
    this.getData()
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}

#app {
  padding-right: 5em;
  padding-left: 5em;
  display: grid;
  grid-gap: 1rem;
  grid-template-columns: repeat(4, auto);
  align-items: start;
  column-count:4;
  }
</style>
