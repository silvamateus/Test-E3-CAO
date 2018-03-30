  <template>
  <div id="app">
    <infinite-scroll></infinite-scroll>
  </div>
</template>

<script>
import InfiniteScroll from './components/InfiniteScroll.vue'

export default {
  name: 'app',
  components: {
    InfiniteScroll
  }
}
</script>

<style lang="scss">
  body{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  #app{
    padding-top: 1em;
    width: 100%;
    display: flex;
    justify-content: center;
  }
</style>
