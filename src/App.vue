<template>
	<div class="container">
		<Header
			title="Tasks"
			@show-add-task="showAddTask"
			:showTaskInput="showTaskInput"
		/>
		<div v-show="showTaskInput">
			<AddTask @add-task="addTask" />
		</div>
		<Tasks :tasks="tasks" @delete-task="onDelete" @remind-task="onRemind" />
	</div>
</template>

<script>
	import Header from "./components/Header.vue";
	import Tasks from "./components/Tasks.vue";
	import AddTask from "./components/AddTask.vue";

	export default {
		name: "App",
		components: {
			Header,
			Tasks,
			AddTask,
		},
		data() {
			return {
				tasks: [],
				showTaskInput: false,
			};
		},
		methods: {
			showAddTask() {
				this.showTaskInput = !this.showTaskInput;
			},
			addTask(task) {
				this.tasks = [...this.tasks, task];
			},
			onDelete(id) {
				if (confirm(`Are you sure you want to delete this task?`)) {
					this.tasks = this.tasks.filter((task) => task.id !== id);
				}
			},
			onRemind(id) {
				this.tasks.map((task) => {
					if (task.id === id) {
						task.reminder = !task.reminder;
					}
				});
			},
		},
		created() {
			this.tasks = [
				{
					id: 1,
					title: "Run",
					day: "March 5th at 2:30pm",
					reminder: true,
				},
				{
					id: 2,
					title: "Fly",
					day: "March 7th at 2:30pm",
					reminder: false,
				},
			];
		},
	};
</script>

<style>
	@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");

	* {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	body {
		font-family: "Poppins", sans-serif;
	}

	.container {
		max-width: 500px;
		margin: 30px auto;
		overflow: auto;
		min-height: 300px;
		border: 1px solid steelblue;
		padding: 30px;
		border-radius: 5px;
	}
</style>
