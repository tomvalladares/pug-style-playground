/**
 * 404
 */

<script>
export default {
	name: "Lost"
}
</script>

<template lang="pug">

div.d-flex.page
	div.message.d-flex
		div.title-wrapper.d-flex
			h1.title Oh No!,<br> Nos hemos perdido
			router-link(to='/').button Go Home
		img(src="../images/svg/13.svg").p-absolute

</template>

<style lang="stylus" scoped>

@require "../stylus/color"

	.page
		flex-direction	column
		justify-content center
		align-items 	center
		width			100vw
		height			100vh

	.title
		font-size 		80px
		color  			color-shadow

	.title-wrapper
		flex-direction	column
		min-width 		450px

	.message
		justify-content flex-start
		align-items 	center
		width 			100vw
		padding 		60px
		height 			100vh
	img
		left 			450px
		min-width		1000px
		max-height		1000px


</style>
