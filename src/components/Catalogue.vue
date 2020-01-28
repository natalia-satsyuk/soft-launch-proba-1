<template>
	<div class="catalogue">

		<div class="container">
			<h1 class="text-center">Catalogue:</h1>
			<ul id="list">
				<li v-for="item in items"> {{ item.name }} </li>	
			</ul>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Catalogue',
		el: '#list',
		data: {			
			items: [
				{ name: 'first' },
				{ name: 'second' },
				{ name: 'third' }
			]
		},
		
		// mounted() {
		// 	axios.get("https://api.nytimes.com/svc/topstories/2/home.json?api-key=your_api_key")
  //   		.then(response => {this.results = response.data.results})
		// },

		// methods: {
		// 	getData: function(itemGetFromApi) {
		// 		this.item = itemGetFromApi
		// 	}
		// }
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
		align-items: center;
	}
</style>

