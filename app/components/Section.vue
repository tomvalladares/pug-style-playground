/**
 * Section
 */

<script>
export default {
	name: "Section",

	data: () => ({
		contador: 0,
		posY: 0,
		posX: 0,
		steps:20,
		turboId: '',
		isTurbOn: 'Off',
		showButton: false,
		posBoton: {
			top: '500px',
			left: '500px'
		}
	}),
	methods: {
		randomizer: function() {
			this.contador +=1
			this.randomizerPos()
			this.posBoton.top  = this.posY
			this.posBoton.left = this.posX
			this.isEnough()
		},
		isEnough() {
			if(this.contador >= 5) {
				return this.showButton = true
			}
		},
		randomizerPos: function() {
			this.posY = Math.floor(Math.random() * (window.innerHeight - 200)) + 'px'

			this.posX = Math.floor(Math.random() * (window.innerWidth - 200)) + 'px'
		},
		startTurbo(){
			if(this.isTurbOn =='Off'){
				this.isTurbOn = 'On'
				this.turboId = setInterval( () => {
					this.randomizer()
				}, 20)
			} else {
				this.isTurbOn = 'Off'
				clearInterval(this.turboId)
			}
		},
		goUp(){
			let posicionY = parseInt(this.posBoton.top)

			console.log('posY: '+posicionY)

			if(posicionY < 0){
				posicionY = window.innerHeight-200
			} else {
				posicionY -= this.steps
			}

			this.posBoton.top = posicionY + 'px'
		},
		goDown() {
			let posicionY = parseInt(this.posBoton.top)

			console.log('posY: '+ posicionY)

			if(posicionY > window.innerHeight-200){
				posicionY = -20
			} else {
				posicionY += this.steps
			}

			this.posBoton.top = posicionY + 'px'
		},
		goLeft() {
			let posicionX = parseInt(this.posBoton.left)

			console.log('posX: '+posicionX)

			if(posicionX < 0){
				posicionX = window.innerHeight-200
			} else {
				posicionX -= this.steps
			}

			this.posBoton.left = posicionX + 'px'
		},
		goRight() {
			let posicionX = parseInt(this.posBoton.left)

			console.log('posX: '+posicionX)

			if(posicionX > window.innerHeight-150){
				posicionX = 0
			} else {
				posicionX += this.steps
			}

				this.posBoton.left = posicionX + 'px'
		},
	},
	mounted () {
		// window.addEventListener ('keydown' , (event) => {
		// 	if(event.key ==='ArrowUp'){
		// 		this.goUp()
		// 	}else if(event.key === 'ArrowDown'){
		// 		this.goDown()
		// 	} else if(event.key === 'ArrowLeft') {
		// 		this.goLeft()
		// 	} else if(event.key === 'ArrowRight') {
		// 		this.goRight()
		// 	} else if (event.key === 'Enter'){
		// 		this.randomizer()
		// 	}
		// })

			window.addEventListener ('keydown', (event) => {
				switch(event.key) {
					case 'ArrowUp': this.goUp()
						break
					case 'ArrowDown': this.goDown()
						break
					case 'ArrowLeft': this.goLeft()
						break
					case 'ArrowRight': this.goRight()
						break
				}


			})
	},
}

</script>

<template lang="pug">

.section

	p.paragraph Usa las flechas para mover el objeto o enter para randomizar su posición
	div.d-flex
		div(:style="posBoton").botonera-vertical.d-flex.p-absolute
			button(@click="goUp").tecla +
			div.d-flex.botonera-horizontal
				button(@click="goLeft").tecla -
				button(@click="randomizer" ).boton-round Click Me <br> {{contador}}
				button(@click="goRight").tecla +
			button(@click="goDown").tecla -
		button(@click="startTurbo").button Turbo! {{isTurbOn}}
		router-link(to='/' v-if="showButton").button Back!

</template>

<style lang="stylus" scoped>
@import "../stylus/color"

.paragraph
	p
	text-align 		center
	color 			color-shadow

.botonera-vertical
	flex-direction	column
	align-items 	center
	justify-content	center
	margin			10px

.botonera-horizontal
	align-items 	center

.tecla
	background		color-accent
	width			30px
	height			30px
	margin			10px
	border-radius	30px
	&:hover
		background	color-shadow
		color  		color-pale

.boton-round
	background 		color-shadow
	width 			100px
	height			100px
	border-radius	100px
	color			color-pale

</style>
