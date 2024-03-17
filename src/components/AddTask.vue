<template>
	<form @submit="onSubmit">
		<label for="name">Task name</label>
		<input
			type="text"
			id="name"
			name="name"
			v-model="name"
			placeholder="Add task name"
			required
		/>

		<label for="date">Date</label>
		<input
			type="text"
			id="date"
			name="date"
			v-model="date"
			placeholder="Date"
			required
		/>

		<div>
			<label for="reminder">Set reminder</label>
			<input
				name="reminder"
				type="checkbox"
				v-model="reminder"
				placeholder="Task name"
			/>
		</div>

		<input type="submit" value="Add" />
	</form>
</template>

<script>
	export default {
		name: "AddTask",
		methods: {
			onSubmit(e) {
				e.preventDefault();

				const task = {
					id: Math.floor(Math.random() * 1000000000),
					title: this.name,
					day: this.date,
					reminder: this.reminder,
				};

				this.$emit("add-task", task);

				this.name = "";
				this.date = "";
				this.reminder = false;
			},
		},
		data() {
			return {
				name: "",
				date: "",
				reminder: false,
			};
		},
	};
</script>

<style scoped>
	form {
		margin: 0.5rem;
		padding: 0.5rem;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		background: rgb(227, 238, 254);
	}

	input {
		padding: 0.35rem;
		border: 1px solid rgb(198, 193, 193);
	}

	input:focus {
		outline: none;
		border: 1px solid green;
	}

	input[type="checkbox"] {
		margin-left: 1rem;
		transform: scale(1.2);
	}

	input[type="submit"] {
		background: #3780f6;
		color: white;
		padding: 0.5rem 0;
	}

	input[type="submit"]:hover {
		opacity: 0.8;
	}
</style>
