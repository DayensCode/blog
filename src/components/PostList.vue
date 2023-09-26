<template>
	<div>
		<h3>Список пользователей</h3>
		<post-item v-for="post in postsList" :obj="post" />
	</div>
</template>


<script>
import PostItem from "@/components/PostItem.vue";
export default {
	components: {PostItem},
	props: {
		postsList: {
			type: Array,
		}
	}
}
</script>


<style scoped>
.post {
	padding: 15px;
	border: 2px solid green;
	margin-top: 15px;
}
</style>