<template>
	<p>Reaction time - {{ score }} ms</p>
	<p class="rank">{{ rank }}</p>
</template>

<script>
export default {
	name: "Results",
	props: ["score"],
	data() {
		return {
			rank: null,
		};
	},
	mounted() {
		if (this.score < 250) this.rank = "You're fast";
		else if (this.rank < 400) this.rank = "Fast enough";
		else this.rank = "You're slow";
	},
};
</script>

<style scoped>
.rank {
	font-size: 1.4em;
	color: #0faf87;
	font-weight: bold;
}
</style>
