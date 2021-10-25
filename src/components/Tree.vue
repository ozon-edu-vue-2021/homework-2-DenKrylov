<template>
	<ul id="tree">
		<tree-str :item="data" />
	</ul>
</template>

<script>
import Data from '../../public/static/node_modules.json';
import TreeStr from './TreeStr.vue';

export default({
	name: 'tree',
	data: function() {
		return {
			data: Data,
		}
	},
	compnents: {
		TreeStr,
	}
})
</script>
