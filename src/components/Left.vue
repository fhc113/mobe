<template>
<div class="app">
    
<el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
   <router-link tag="lo" to="/index2">
  <el-submenu index="1">
     <template slot="title">
      <i class="el-icon-s-home"></i>
    </template>
  </el-submenu>
</router-link>
  <el-submenu index="2">
    <template slot="title">
      <i class="el-icon-s-platform"></i>
        <span slot="title">1</span>
    </template>
    <el-menu-item-group>
      <span slot="title">CRM</span>
      <router-link tag="lo" to="/cha"><el-menu-item index="2-1">发现</el-menu-item></router-link>
      
      <router-link tag="lo" to="/kehu"><el-menu-item index="2-1">客户公共池</el-menu-item></router-link>
      <router-link tag="lo" to="/xiang"><el-menu-item index="2-1">线索</el-menu-item></router-link>
      <router-link tag="lo" to="/shang"><el-menu-item index="2-1">商机</el-menu-item></router-link>
      <router-link tag="lo" to="/kehu"><el-menu-item index="2-1">客户管理</el-menu-item></router-link>
      <!-- <router-link tag="lo" to="/kehu"><el-menu-item index="2-1">合同</el-menu-item></router-link>
      <router-link tag="lo" to="/kehu"><el-menu-item index="2-1">联系人</el-menu-item></router-link> -->
      <router-link tag="lo" to="/xiansou"><el-menu-item index="2-1">销售任务</el-menu-item></router-link>
      <router-link tag="lo" to="/lian"><el-menu-item index="2-1">日程</el-menu-item></router-link>
      <router-link tag="lo" to="/ditu"><el-menu-item index="2-1">外勤</el-menu-item></router-link>
      <router-link tag="lo" to="/guan"><el-menu-item index="2-1">产品</el-menu-item></router-link>
    </el-menu-item-group>
   
  </el-submenu>
  
   <el-submenu index="3">
    <template slot="title">
      <i class="el-icon-picture-outline-round"></i>
        <span slot="title">1</span>
    </template>
    <el-menu-item-group>
      <span slot="title">统计分析</span>
      <router-link tag="lo" to="/yibiao"><el-menu-item index="2-1">仪表盘</el-menu-item></router-link>
      
      <router-link tag="lo" to="/bao"><el-menu-item index="2-1">数据报表</el-menu-item></router-link>
      <router-link tag="lo" to="/xiang"><el-menu-item index="2-1">销售分析</el-menu-item></router-link>
      <router-link tag="lo" to="/kefen"><el-menu-item index="2-1">客户分析</el-menu-item></router-link>
    </el-menu-item-group>
   
  </el-submenu>
  <router-link tag="lo" to="/zhishi">
  <el-menu-item index="4">
    <i class="el-icon-setting"></i>
  
  </el-menu-item>
  </router-link>
  
</el-menu>

</div>
  


</template>
<style>
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }
  ::v-deep .el-menu-item{
      padding: 0px 10px;
  }
  .emi{
    padding: 5px 0px;
    font-size: 11px;
  }
  .el-menu {
    border-right: none;
    list-style: none;
    position: relative;
    margin: 0;
    padding-left: 0;
    background-color: #FFF;
}
</style>

<script>
  export default {
    data() {
      return {
        isCollapse: true
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>