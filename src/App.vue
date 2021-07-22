<template>
	<h1>Conversor de Moedas</h1>
	<h3>Dólar Americano</h3>
	<div class="line">
		<Converter currencyA="USD" currencyB="BRL" />
		<Converter currencyA="BRL" currencyB="USD" />
	</div>
	<h3>Euro</h3>
	<div class="line">
		<Converter currencyA="EUR" currencyB="BRL" />
		<Converter currencyA="BRL" currencyB="EUR" />
	</div>
	<h3>Libra Esterlina</h3>
	<div class="line">
		<Converter currencyA="GBP" currencyB="BRL" />
		<Converter currencyA="BRL" currencyB="GBP" />
	</div>
</template>

<script>
import Converter from './components/Converter.vue';

export default {
	name: 'App',
	components: {
		Converter,
	},
};
</script>

<style>
#app {
	margin: 0;
	font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
		'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
		sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	max-width: 900px;
	margin: auto;
}

h1,
h2 {
	text-align: center;
}

h3 {
	text-align: center;
	margin-top: 50px;
	border-top: 1px solid #ddd;
	padding-top: 20px;
}

.line {
	margin-top: 40px;
	display: flex;
	justify-content: space-around;
}
</style>
