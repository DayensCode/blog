<template>
	<div class="post">
		<div>Название: {{ obj.title }}</div>
		<div>Описание: {{ obj.body }}</div>
	</div>
</template>


<script>
export default {
	props: {
		obj: {
			type: Object,
			reguired: true,
		}
	}

}
</script>


<style scoped>

</style>