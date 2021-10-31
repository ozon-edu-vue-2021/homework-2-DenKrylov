<template>
  <div id="app">
    <pwd class="pwd" :path="path"/>
    <ul id="tree" class="tree">
      <tree :item="data" :pwd="pwd" :onPath="onPath"></tree>
    </ul>
  </div>
</template>

<script>
import data from '../public/static/node_modules.json';
import Tree from './components/Tree.vue';
import Pwd from './components/Pwd.vue';

export default {
  name: 'App',
  data: function() {
    return {
      data: data,
      path: "",
      pwd: ""
    }
  },
  components: {
    Tree,
    Pwd
  },
  methods: {
    onPath(pwd) {
      this.path = pwd;
    }
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
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column;
}
.tree {
  margin-top: 30px;
}
.pwd {
  position: absolute;
  display: flex;
  align-items: center;
  top: 0;
  left: 0;
  width: 100%;
  height: 25px;
  border-bottom: 1px solid rgb(65, 184, 131);
  background: rgba(49, 54, 59, 1);
}
</style>
