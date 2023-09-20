<template>
	<form @submit.prevent>
		<h4>Создание поста</h4>
		<input v-model="obj.title" class="input" type="text" placeholder="Название">
		<input v-model="obj.body" class="input" type="text" placeholder="Описание">
		<button class="btn" @click="createPost">Создать</button>
	</form>
</template>


<script>
export default {
	data() {
		return {
			obj: {
				"id": "",
				"title": "",
				"body": "",
			}
		}
	},
	methods: {
		createPost() {
			this.obj.id = Date.now();
			this.$emit('create', this.obj);
			this.obj = {
				"title": "",
				"body": "",
			}
		}
	},
}
</script>


<style>
form {
	display: flex;
	flex-direction: column;
}

.btn {
	margin-top: 15px;
	align-self: flex-end;
	padding: 10px 15px;
	background-color: transparent;
	color: green;
	border: 1px solid green
}

.input {
	width: 100%;
	border: 1px solid green;
	padding: 10px 15px;
	margin-top: 10px;
}
</style>