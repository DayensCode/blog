<template>
	<div class="app">
		<post-form @create="createPost"/>
		<post-list :postsList="posts"/>
	</div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
	components: {
		PostForm, PostList
	},

	data() {
		return {
			posts: [
				{id: 1, title: "first post", body: "Описание поста1"},
				{id: 2, title: "second post", body: "Описание поста2"},
				{id: 3, title: "third post", body: "Описание поста3"},
			],
		}
	},

	methods: {
		createPost(post) {
			this.posts.push(post);
		}
	},
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
</style>