<template>
	<ul id="tree">
		<tree-branch :item="data"></tree-branch>
	</ul>
</template>

<script>
import Data from '../../public/static/node_modules.json';
import TreeBranch from './TreeBranch.vue';

export default{
	name: 'tree',
	data: function() {
		return {
			data: Data,
		}
	},
	components: {
		TreeBranch,
	}
}
</script>
