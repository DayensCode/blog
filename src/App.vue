<template>
<div class="app">
	<form @submit.prevent>
		<h4>Создание поста</h4>
		<input v-bind:value="title" @input="titleChangeHandler" class="input" type="text" placeholder="Название">
		<input v-bind:value="body" @input="bodyChangeHandler" class="input" type="text" placeholder="Описание">
		<button class="btn" @click="createPost">Создать</button>
	</form>
	<div class="post" v-for="post in posts">
		<div>Название: {{ post.title }}</div>
		<div>Описание: {{ post.body }}</div>
	</div>
</div>
</template>

<script>
export default {
	data() {
		return {
			posts: [
				{id: 1, title: "first post", body: "Описание поста1"},
				{id: 2, title: "second post", body: "Описание поста2"},
				{id: 3, title: "third post", body: "Описание поста3"},
			],
			title: "",
			body: "",
		}
	},

	methods: {
		createPost() {
			const newPost = {
			id: Date.now(),
			title: this.title,
			body: this.body,
			}
			this.posts.push(newPost);
			this.title="";
			this.body="";
		},
		titleChangeHandler(event) {
			this.title = event.target.value;
		},
		bodyChangeHandler(event) {
			this.body = event.target.value;
		},
	}
}
</script>

<style>
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

.app {
	padding: 20px;
}

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

.post {
	padding: 15px;
	border: 2px solid green;
	margin-top: 15px;
}

.input {
	width: 100%;
	border: 1px solid green;
	padding: 10px 15px;
	margin-top: 10px;
}
</style>