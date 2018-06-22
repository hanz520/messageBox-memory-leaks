<template>
  <div>
    <h3>i am page 2</h3>
    <el-input class="a2" value="a2" type="text"></el-input>
    <el-input class="b2" value="b2" type="text"></el-input>
    <el-input class="c2" value="c2" type="text"></el-input>
    <el-input class="d2" value="d2" type="text"></el-input>
    <el-input class="e2" value="e2" type="text"></el-input>
    <el-button @click="callMessageBox">click me</el-button>
  </div>
</template>

<script>
export default {
  name: 'page2',
  methods: {
    callMessageBox() {
      this.$confirm('调用一次confirm', '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          type: 'warning'
        }).then(() => {
        }).catch(() => {
        });
    }
  }
}
</script>

