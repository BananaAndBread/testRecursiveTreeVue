<template>
  <div id="app">
    <treeNode :text="tree.text" :childs=tree.childs></treeNode>
  </div>
</template>

<script>
import treeNode from "@/components/TreeNode";

export default {
  name: 'App',
  components: {
    treeNode
  },
  data() {
    return {
      tree: {
      text: 'root',
          childs: [
        {
          text: 'item1',
          childs: [
            {
              text: 'item1.1'
            },
            {
              text: 'item1.2',
              childs: [
                {
                  text: 'item1.2.1'
                }
              ]
            }
          ]
        },
        {
          text: 'item2'
        }
      ]
    }}
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
