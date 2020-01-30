<template>
	<div class="catalogue">

		<div class="container">
			<h1 class="text-center">Catalogue:</h1>
			<ul id="list">
				<li v-for="(item, idx) in items" :key="idx">
					{{ item.title }}
				</li>	
			</ul>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Catalogue',
		data() {
			return {
				items: []
			}
		},

		mounted() {
			this.postData()
		},

		methods: {
			postData() {
			    return fetch('https://jsonplaceholder.typicode.com/posts')
			  .then(response => response.json())
			  .then(json => this.items = json )
			},
		}
	}
</script>

<style scoped >
	.container {
		width: 1200px;
		margin: 0 auto;
	}

	ul {
		display: flex;
		flex-direction: column; 
		margin: 0 auto;
		max-width: 500px;
	}
</style>

