<template>
	<li id="tree">
		<div 
			:class="branch()"
			@click="action()"
			@keyup.enter="action()"
			tabindex="0"
		>
			<img :src="getIcon()" :alt="getType()">
			<span :class="highlight()">{{ name }}</span>
		</div>
		<ul v-if="isOpen">
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
			pwd: '',
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
			} 
		},
		branch: function() {
			if(this.type == 'directory') {
				return 'folder branch';
			} else {
				return 'branch';
			}
		},
		highlight: function() {
			if(this.type != 'directory') {
				return 'highlight';
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
	flex-direction: row;
	align-items: center;
}
.branch:focus {
	color: rgb(61, 174, 233);
	outline: none;
}
.folder {
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.highlight {
	user-select: all;
}
span::selection {
    color: rgba(49, 54, 59, 1);
	background: rgb(61, 174, 233);
}
span:hover {
	text-decoration: underline;
}

</style>