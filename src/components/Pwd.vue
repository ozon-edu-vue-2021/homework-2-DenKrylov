<template>
	<div>
		<span>PWD: {{ item }}</span>
	</div>
</template>

<script>

export default{
	name: 'pwd',
	props: {
		item: String,
	},
}
</script>

<style scoped>
span {
	margin-left: 10px;
}
</style>