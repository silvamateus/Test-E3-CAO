	<template>
	<div id="app">
		<infinite-scroll></infinite-scroll>
	</div>
</template>

<script>
import InfiniteScroll from './components/InfiniteScroll.vue'

export default {
	data(){
		return{
			posts: []
		}
	},
	name: 'app',
	components: {
		InfiniteScroll
	},
	methods:{
		getData: function getData(){
			fetch('http://www.mocky.io/v2/5abea2d12e00004d006f7e35')
				.then(res => res.json())
				.then(res => this.posts = this.posts.concat(res.posts))
		}
	}
}
</script>

<style lang="scss">
	*{
		box-sizing: border-box;
	}

	body{
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
