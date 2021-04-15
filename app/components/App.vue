/**
 * App
 */

<script>

import Vue       from "vue"
import VueRouter from "vue-router"

import Home    	from "./Home.vue"
import Section 	from "./Section.vue"
import Lost	from "./Lost.vue"
import Grid from "./Grid.vue"
import Grid1 from "./Grid1.vue"

Vue.use(VueRouter)

// Routes
const routes = [

	{
		path     : "/",
		component:  Home
	},
	{
		path     : "/section",
		component: Section
	},
	{
		path	: "/404",
		component: Lost
	},
	{
		path	: "/grid",
		component: Grid
	},
	{
		path	: "/grid1",
		component: Grid1
	},
	// not found
	{
		path    : "*",
		redirect: "/404"
	}
]

export default {

	name: "App",

	router: new VueRouter({ routes })
}
</script>

<template lang="pug">

transition(name="fade" mode="out-in" :duration="{ enter: 300, leave: 300 }" appear)
	router-view

</template>

