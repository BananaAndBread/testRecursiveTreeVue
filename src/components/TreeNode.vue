<template>
  <div @click.stop = 'someMethod'>
    <div>{{ text }}</div>
    <TreeNode
        :ref="String(index)"
        v-for="(node, index) in childs"
        v-bind:key="index"
        :childs="node.childs"
        :text="node.text"
    >`
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
  name: 'TreeNode',
  methods: {
    someMethod(){
      console.log(this.text)
      let index = 0
      if (this.childs && this.childs.length > 0) {
        for (index; index < this.childs.length; index++) {
          this.$refs[String(index)][0].someMethod()
        }
      }
    }
  }
}
</script>

<style scoped>


</style>