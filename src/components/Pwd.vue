<template>
	<div>
		<span>Path:</span>
		<span>{{ path }}</span>
	</div>
</template>

<script>
export default{
	name: 'pwd',
	props: {
		path: String,
	},
}
</script>

<style scoped>
span {
	margin-left: 10px;
}
</style>