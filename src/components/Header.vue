<template>
	<header>
		<h1>{{ title }}</h1>
		<Button
			:text="showTaskInput ? 'Close' : 'Add task'"
			:color="showTaskInput ? '#f58a42' : '#4287f5'"
			@clicked="$emit('show-add-task')"
		/>
	</header>
</template>

<script>
	import Button from "./Button.vue";
	export default {
		name: "Header",
		props: {
			title: String,
			showTaskInput: Boolean,
		},
		components: {
			Button,
		},
		emits: ["show-add-task"],
	};
</script>

<style scoped>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 1rem;
	}
</style>