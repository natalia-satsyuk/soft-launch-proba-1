<template>
	<div class="catalogue">

		<div class="container">
			<h1 class="text-center">Catalogue:</h1>
			<ul id="list">
				<li v-for="(currency, idx) in info" :key="idx">
					{{ currency.description }}
					<span>
						<span v-html="currency.symbol"></span>
						{{ currency.rate_float | currencydecimal }}
					</span>
					
				</li>	
			</ul>
		</div>
	</div>
</template>


<script src="https://unpkg.com/axios/dist/axios.min.js"></script>

<!-- eslint-disable -->
<script>

	import axios from 'axios';

	export default {
		name: 'CatalogueAxios',
		data() {
			return {
				info: null,
				loading: true,
				errored: false
			}
		},

		filters: {
			currencydecimal (value) {
				return value.toFixed(2)
			}
		},

		mounted() {
			axios
			.get('https://api.coindesk.com/v1/bpi/currentprice.json')
			.then(response => {
				this.info = response.data.bpi;
			})
			.catch(error => {
				console.log(error);
				this.errored = true;
			}) 
			.finally(() => (this.loading = false))
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

