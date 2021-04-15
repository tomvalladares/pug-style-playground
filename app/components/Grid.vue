<template lang="pug">
	div
		div.container
			h1.elem1 Semana
			h1.elem2 Fin de semana
			h1 lunes
			h1 Martes
			h1 Miercoles
			h1 Jueves
			h1 Viernes
			h1 Sábado
			h1 Domingo
			h1(v-for="(elem,index) in 30" :key="elem.id").elemento1 {{elem}}
			router-link(to='/grid1').button Ejercicio 1

</template>

<script>
	export default {
		data() {
			return {
				colores: []
			}
		},
	}
</script>

<style lang="stylus" scoped>
@require "../stylus/color"
.container
	display 				grid
	width					100vw
	height					100vh
	padding 				50px
	grid-template-columns 	1fr 1fr 1fr 1fr 1fr 1fr 1fr
	grid-template-rows    	30px 30px auto
	grid-gap 				1px


.elemento1
	border 					1px solid color-accent2
	&:hover
		background			color-pale

.elem1
	border 					1px solid color-accent2
	grid-column-end			span 5
	text-align 				center
	color  					color-accent

.elem2
	border 					1px solid color-accent2
	grid-column-end			span 2
	text-align 				center
	color  					color-accent


</style>