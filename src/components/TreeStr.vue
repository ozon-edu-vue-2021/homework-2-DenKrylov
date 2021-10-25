<template>
	<li id="TreeStr" class="tree-str">
		<span></span>
	</li>
</template>

<script>

export default({
	name: 'TreeStr',
	props: {
		item: Object,
	},
	data: function() {
		return {
			type: this.item.type,
		}
	}
})
</script>

<style scoped>
.tree-str {
	display: flex;
	align-items: center;
	height: 20px;
}
</style>