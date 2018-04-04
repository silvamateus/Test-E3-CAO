<template>
  <header class="top-bar">
    <span class="menu"><i class="fas fa-bars"></i></span>
    <div class="search-box">
      <input type="search" v-model="searchText" name="search" id="search-bar">
      <button @click="searchThings" id="search-button">
        <i class="fas fa-search"></i>
      </button>
    </div>
    <p>CADE O TEXTO</p>
  </header>
</template>

<script>
export default {
  data() {
    return {
      searchText: ''
    }
  },
  watch: {
    searchText(val, oldVal) {
      this.searchText = val
    }
  },
  methods: {
    searchThings(query){
     this.$emit('searchQuery', this.searchText)
    }
  }
}
</script>

<style lang="scss" scoped>
  .top-bar {
    margin: 0;
    display: flex;
    justify-content: space-between;
    //position: fixed;
    p {
      margin: 0;
    }
    .menu {
      border: 1px solid #bbb;
      border-radius: .3rem;
    }

  }
  .search-box {
      margin: 0;
      #search-bar {
        text-align: left;
       width: 25rem;
        padding-bottom: .3rem;
        border-radius: .3rem;
      }
      #search-button{
        position: absolute;
        border: 1px solid #bbb;
        border-radius: .3rem
      }
    }
</style>
