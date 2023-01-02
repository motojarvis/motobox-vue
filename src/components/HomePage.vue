<template>
  <el-col :span="24">
      <TopLine/>
      <el-row>
        <el-col :span="8">
          <LeftScreen/>
        </el-col>
        <el-col :span="8">
          <LeftScreen/>
        </el-col>
        <el-col :span="8">
          <LeftScreen/>
        </el-col>
      </el-row>
    </el-col>
</template>

<script>
import TopLine from './TopLine.vue'
import LeftScreen from './LeftScreen.vue'

export default {
  name: 'HomePage',
  components:{
    TopLine,
    LeftScreen
  }
}
</script>

<style>
  .el-row {
    margin-bottom: 1px;
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  
  /* 主体 */
  .grid-content {
    border-radius: 4px; 
    min-height: auto;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>