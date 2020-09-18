<template>
  <div class="tree-menu">
    <div>{{ text }}</div>
    <TreeNode
        v-bind:key="index"
        v-for="(node, index) in childs"
        :childs="node.childs"
        :label="node.text"
    >
    </TreeNode>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
    },
    childs: {
      type: Array
    }
  },
  name: 'TreeNode'
}
</script>

<style scoped>


</style>