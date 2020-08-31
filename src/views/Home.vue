<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png" />
		<Star :score="score"></Star>
		<HelloWorld msg="Welcome to Your Vue.js App" />
	</div>
</template>

<script>
	// @ is an alias to /src
	import HelloWorld from "@/components/HelloWorld.vue";
	import Star from "@/components/Star.vue";
	export default {
		name: "Home",
		components: {
			HelloWorld,
			Star,
		},
		data() {
			return {
				score: 2.5
			}
		},
	};
</script>
