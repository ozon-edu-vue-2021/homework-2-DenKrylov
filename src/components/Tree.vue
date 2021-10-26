<template>
	<li id="tree">
		<div :class="branch()" @click="action()">
			<img v-bind:src="getIcon()" :alt="getType()">
			<span>{{ name }}</span>
		</div>
		<ul v-show="isOpen">
			<tree
				v-for="(el, i) in item.contents"
				:key="i"
				:item=el
			></tree>
		</ul>
	</li>
</template>

<script>

export default{
	name: 'tree',
	props: {
		item: Object,
	},
	data: function() {
		return {
			isOpen: false,
			name: this.item.name,
			type: this.item.type,
		}
	},
	methods: {
		getIcon: function() {
			if(this.type == 'directory') {
				return 'assets/folder.svg';
			} else if(this.type == 'file') {
				return 'assets/description.svg';
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
		},
		action: function() {
			if(this.type == 'directory') {
				this.isOpen = !this.isOpen;
			} else if(this.type != 'directory') {
				document.getSelection().setBaseAndExtent();
			}
		},
		branch: function() {
			if(this.type == 'directory') {
				return 'folder branch';
			} else {
				return 'branch';
			}
		}
	}
}
</script>

<style scoped>
li {
	display: flex;
	flex-direction: column;
	margin-left: 25px;
	cursor: pointer;
}
.branch {
	display: flex;
	align-items: center;
}
span::selection {
    color: rgba(49, 54, 59, 1);
	background: rgb(65, 184, 131);
}
.folder {
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

</style>