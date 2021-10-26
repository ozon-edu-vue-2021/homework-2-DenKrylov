<template>
  <div id="app">
    <ul id="tree" class="tree">
      <tree :item="data"></tree>
    </ul>
  </div>
</template>

<script>
import Data from '../public/static/node_modules1.json';
import Tree from './components/Tree.vue';

export default {
  name: 'App',
  data: function() {
		return {
			data: Data,
		}
	},
	components: {
		Tree,
	}
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  background: rgba(49, 54, 59, 1);
  color: rgb(65, 184, 131);
}
ul {
  display: flex;
  flex-direction: column;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
}
</style>
