<template>
	<div class="block" v-if="isShow" @click="stopTimer">Click me</div>
</template>

<script>
export default {
	name: "Block",
	props: ["delay"],
	data() {
		return {
			isShow: false,
			timer: null,
			reactionTime: 0,
		};
	},
	mounted() {
		setTimeout(() => {
			this.isShow = true;
			this.startTimer();
		}, this.delay);
	},
	methods: {
		startTimer() {
			setInterval(() => {
				this.reactionTime += 10;
			}, 10);
		},
		stopTimer() {
			clearInterval(this.timer);
			this.$emit("end", this.reactionTime);
		},
	},
};
</script>

<style scoped>
.block {
	width: 400px;
	border-radius: 20px;
	background: #0faf87;
	color: white;
	text-align: center;
	padding: 100px 0;
	margin: 40px auto;
}
</style>
