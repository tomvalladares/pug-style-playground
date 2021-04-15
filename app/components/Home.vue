/**
 * Home
 */

<script>

export default {

	name: "Home",

	data: () => ({
					text: "Hello World from Home!",
					text2 :"Bienvenido" }),
	mounted () {
		console.log('hello sapo');
	},
}
</script>

<template lang="pug">

div.home.d-flex

	div.wrapper.d-flex

		h1.title Bienvenido a mi súper página de prueba

		p.paragraph This is a dummy text to test the development in pug and stylus. this is a dummy text to test the development in pug and stylus. this is a dummy text to test the development in pug and stylus.

		router-link(to='/section').button Ir a la sección mágica
		router-link(to='/grid').button Ir a la sección ordenada
		router-link(to='/404').button Ir a la sección perdida

</template>

<style lang="stylus" scoped>

@import "../stylus/color"

.home
	height          100vh
	flex-direction	column
	justify-content center
	align-items 	center

.wrapper
	flex-direction	column
	width			500px
	border 			1px solid color-shadow
	border-radius	10px
	padding			25px

h1
	color 			color-accent
	padding-bottom	30px

</style>
