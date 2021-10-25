<template>
	<li id="tree-branch">
		<img v-bind:src="getIcon()" :alt="getType()">
		<span>{{ name }}</span>
	</li>
</template>

<script>

export default{
	name: 'tree-branch',
	props: {
		item: Object,
	},
	data: function() {
		return {
			name: this.item.name,
			type: this.item.type,
		}
	},
	methods: {
		getIcon: function() {
			if(this.type == 'directory') {
				return 'assets/folder.svg';
			} else if(this.type == 'file') {
				return 'assets/file.svg';
			} else if(this.type == 'link') {
				return 'assets/link.svg';
			}
		},
		getType: function() {
			if(this.type == 'directory') {
				return 'folder';
			} else if(this.type == 'file') {
				return 'file';
			} else if(this.type == 'link') {
				return 'link';
			}
		}
	}

}
</script>

<style scoped>
li {
	display: flex;
	align-items: center;
	height: 20px;
	cursor: pointer;
}
</style>