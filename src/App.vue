<template>
  <div id="app">
    <Tree />
  </div>
</template>

<script>
import Tree from './components/Tree.vue';

export default {
  name: 'App',
  components: {
    Tree
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(53, 73, 94);
  margin-top: 60px;
}
</style>
