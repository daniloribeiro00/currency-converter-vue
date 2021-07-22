<template>
	<div class="converter">
		<h2>{{ currencyA }} para {{ currencyB }}</h2>
		<input type="text" v-model="currencyAValue" :placeholder="currencyA" />
		<input type="button" value="Converter" v-on:click="convert" />
		<h2>{{ currencyBValue }}</h2>
	</div>
</template>

<script>
export default {
	name: 'Converter',
	props: ['currencyA', 'currencyB'],
	data() {
		return {
			currencyAValue: '',
			currencyBValue: 0,
		};
	},
	methods: {
		convert() {
			let apiKey = '1cbdacf6b3f12298dac3';
			let from_to = `${this.currencyA}_${this.currencyB}`;
			let url = `https://free.currconv.com/api/v7/convert?q=${from_to}&compact=ultra&apiKey=${apiKey}`;

			fetch(url)
				.then(res => {
                    return res.json();
				})
				.then(json => {
					let change = json[from_to];
					console.log(change);
					this.currencyBValue = (
						parseFloat(this.currencyAValue) * change
					).toFixed(2);
				});
		},
	},
};
</script>

<style scoped>
.converter {
    padding: 10px 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

input {
    border: solid 0.5px;
    border-color: silver; 
}

input:focus {
    outline: 0;
    border-bottom: solid 1px blue;
}
</style>
