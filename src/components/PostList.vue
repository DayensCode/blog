<template>
	<div class="post" v-for="obj in postsList">
		<div>Название: {{ obj.title }}</div>
		<div>Описание: {{ obj.body }}</div>
	</div>
</template>


<script>
export default {
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