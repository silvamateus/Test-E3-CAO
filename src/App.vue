<template>
  <div id="app">
    <infinite-scroll v-for="(post, ind) in posts" :key="ind" :post="post"></infinite-scroll>
    <loading v-if="isLoading"></loading>
  </div>
</template>

<script>
import InfiniteScroll from './components/InfiniteScroll.vue'
import Loading from './components/Loading.vue'

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
      fetch('http://www.mocky.io/v2/5abf98fc2c00005200c3ce3f')
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
  padding-top: 1em;
  padding-left: 5em;
  width: 93%;
  display: flex;
  justify-content: space-between;
}
</style>
