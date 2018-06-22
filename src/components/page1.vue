<template>
  <div>
    <h3>i am page 1</h3>
    <el-input class="a1" value="a1" type="text"></el-input>
    <el-input class="b1" value="b1" type="text"></el-input>
    <el-input class="c1" value="c1" type="text"></el-input>
    <el-input class="d1" value="d1" type="text"></el-input>
    <el-input class="e1" value="e1" type="text"></el-input>
    <el-input class="f1" value="f1" type="text"></el-input>
    <el-input class="g1" value="g1" type="text"></el-input>
    <el-input class="h1" value="h1" type="text"></el-input>
    <el-input class="i1" value="i1" type="text"></el-input>
    <el-input class="j1" value="j1" type="text"></el-input>
    <el-input class="k1" value="k1" type="text"></el-input>
    <el-button @click="callMessageBox">click me</el-button>
  </div>
</template>

<script>
export default {
  name: 'page1',
  methods: {
    callMessageBox() {
      this.$alert('调用一次alert', '标题名称', {
        confirmButtonText: '确定'
      })
    }
  }
}
</script>

