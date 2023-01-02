<template>
    <el-row class="grid-top bg-purple-dark">
        <el-col :span="8">
           <div class="left"> GPS···· GSM····</div>
        </el-col>
        <el-col :span="8">江苏省·苏州市·吴江区</el-col>
        <el-col :span="8">
            <div class="right">
                2022-01-12 09:32:23
            </div>
        </el-col>
    </el-row>
</template>

<script>
export default {
    name:'TopLine',
}
</script>

<style scoped>
    /* 顶栏样式 */
    .grid-top {
        /* border-radius: 4px; */
        min-height: 20px;
        color: #d3dce6;
    }
    .left {
        margin-left: 10%;
        text-align: left;
    }
    .right {
        margin-right: 10%;
        text-align: right;
    }
    .bg-purple-dark {
    background: #202122;
  }
</style>