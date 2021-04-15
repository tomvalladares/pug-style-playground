<template lang="pug">
	div
		div.container
			header.title 	A
			main.title 		B
			footer.title 	C

</template>

<script>
	export default {

	}
</script>

<style lang="stylus" scoped>

@require "../stylus/color"

.container
	text-align 	center
	display 	grid
	height		100vh
	grid-template-rows 1fr 6fr 1fr

.container *
	border 1px solid color-accent

</style>


