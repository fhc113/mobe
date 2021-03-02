<template>
     <el-row class="tac">
  <el-col :span="5">
    <div class="blu">
      <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;margin-bottom:9px;"></i>&nbsp;&nbsp;
       个人设置
    </div>
    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose">
      <el-menu-item index="1">
        <i class="el-icon-menu"></i>
        <span slot="title" @click="flag=0">我的资料</span>
      </el-menu-item>
      <el-submenu index="2">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>个人参数</span>
        </template>
        <el-menu-item-group>
          
          <el-menu-item index="2-1" @click="flag=1">参数设置</el-menu-item>
          <el-menu-item index="2-2" @click="flag=2">常用入组</el-menu-item>
        </el-menu-item-group>
      
      </el-submenu>
      
      <el-submenu index="3">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span slot="title">平台配置</span>
        </template>
        <el-menu-item-group>
          <el-menu-item index="3-1" @click="flag=3">平台配置</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
        <el-submenu index="4">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span slot="title">系统安全</span>
        </template>
        <el-menu-item-group>
          <el-menu-item index="4-1" @click="flag=4">修改密码</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
      
    </el-menu>



  </el-col>
  <el-col :span="1">
    &nbsp;
  </el-col>
  <el-col :span="18">
      <div class="blu">
        <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;margin-bottom:9px;"></i>&nbsp;&nbsp;
        我的资料<span>--</span>    
      </div>
    <div class="dd1" v-if="flag==0">
      <p class="p1"><i class="el-icon-medal"></i> &nbsp;&nbsp;你可以在这里修改个人资料。</p>
      <div class="kk1">
        <p><span class="spa1" style="margin-top:-10px;">头像:</span><img src="../assets/img/touxiang.png" width="35%"></p>
        <p><span class="spa1">员工编号:</span> <span class="spa2">AJ0288288</span></p>
        <p><span class="spa1">姓名:</span> <span class="spa2">彭于晏</span></p>
        <p><span class="spa1">性别:</span> <span class="spa2">男</span></p>
        <p><span class="spa1">生日:</span> <span class="spa2">1991-9-20</span></p>
        <p><span class="spa1">微信:</span> <span class="spa2">zh_jh0920</span></p>
        <p><span class="spa1">电话:</span> <span class="spa2">13734567890</span></p>
        <p><span class="spa1">部门:</span> <span class="spa2">销售1部</span></p>
        <p><span class="spa1">职能:</span> <span class="spa2">销售主管</span></p>
        <p><span class="butt">保存</span></p>
      </div>
    </div>
    <div class="dd2" v-if="flag==1">
      <p class="p1"><i class="el-icon-medal"></i> &nbsp;&nbsp;你可以在这里调整各模块表单数据显示数量或字段顺序等操作。</p>      
    </div>
      <div class="dd3" v-if="flag==2">
      <p class="p1"><i class="el-icon-medal"></i> &nbsp;&nbsp;你可以在这里增加或修改常用用户组。</p>      
    </div>
      <div class="dd4" v-if="flag==3">
      <p class="p1"><i class="el-icon-medal"></i> &nbsp;&nbsp;你可以在这里简单调整系统页面布局以及模块的增减、顺序调整等操作。</p>      
      <div>
        <p>
          首页
        </p>
        <p class="p11"><span>我关注的数据显示板（最多可添加5个，按住鼠标拖动顺序）</span>&nbsp;<select></select><span class="sp3">添加</span>
        <br><br>
        <img src="../assets/img/wode.png" width="90%">
        </p>
          <p class="p11"><span>今日工作（最多可添加4个，按住鼠标拖动顺序）</span>&nbsp;<select></select><span class="sp3">添加</span>
        <br><br>
        <img src="../assets/img/wode2.png" width="90%">
        </p>
          <p class="p12"><span>常用数据看板（最多可添加5个，按住鼠标拖动顺序）</span>&nbsp;<select></select><span class="sp3">添加</span>
        <br><br>
        <img src="../assets/img/wode3.png" width="90%">
        </p>
      </div>
      <div>
         <p>
         &nbsp;&nbsp;&nbsp; 仪表盘
        </p>
        <p class="p13"><span>统计分析-仪表盘页面（最多可添加8个，按住鼠标拖动顺序）</span>&nbsp;<select></select><span class="sp3">添加</span>
        <br><br>
        <img src="../assets/img/wode4.png" width="90%">
        </p>
         <p class="p13"><span></span>&nbsp;
        <br><br><br><br><br><br><br><br>
        </p>
         <p class="p13"><span></span>&nbsp;
        <br><br>
        </p>
      </div>
    </div>
      <div class="dd5" v-if="flag==4">
      <p class="p1"><i class="el-icon-medal"></i> &nbsp;&nbsp;你可以在这里调整各模块表单数据显示数量或字段顺序等操作。</p>      
    </div>
  </el-col>
</el-row>
</template>
<script>
export default {
    name:'geren',
    data(){
      return{
        flag:0
      }
    },
    methods: {
         handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    },
}
</script>
<style scoped>
    ::-webkit-scrollbar {
     width: 0 !important;
   }
   ::-webkit-scrollbar {
     width: 0 !important;height: 0;
   }
   *{
       margin: 0 auto;
       padding: 0 0;

   }.blu span{
       float: right;
       border: 0.5px darkgrey solid;
       border-radius: 5px;
       font-size: 10px;
       font-weight: 400;
       color: darkgrey;
       
        padding: 5px 20px;
        margin-right: 50px;
        margin-top: 7px;
   }
   .el-col_div{
       width: 90%;
   }
   .el-col_div span{
       margin-left: 1px;
       font-size: 8px;
       color: darkgrey;
   }
   .blu i{
       margin-left: 20px;
   }
   .ddd{
       margin-top: 10px;    
   }
   .el-icon-arrow-right:before{
    content: "";
    }
    .el-timeline-item__wrapper{
    position: relative;
    padding-left: 28px;
    border-bottom: 0.5px darkgrey solid;
    }
    .el-timeline {
    margin: 0;
    /* font-size: 14px; */
    /* list-style: none; */
    }
    .el-timeline[data-v-b2a1ec74]{
    margin: 0px 1px;
    /* font-size: 14px; */
    /* list-style: none; */
}
   .select{
       padding: 3px 5px;
       margin: 8px 0;
       border-radius:4px; 
       width: 70%;
       font-size: 10px;
   }
  .sele{
        padding: 3px 5px;
       margin: 8px 0;
       border-radius:4px; 
       width: 10%;
       font-size: 10px;
       /* border-right: #99a9bf 0.5px solid; */
  }
   .blu{
       border-bottom: cyan 1.5px solid;
   }
  .el-row {
    margin-bottom: 20px;
  }
  .el-icon-printer{
      font-size: 20px;
  }
  .el-col {
    border-radius: 4px;
  }
  /* .bg-purple-dark {
    background: #99a9bf;
  } */
  .el-collapse-item__header {
    display: -webkit-box;
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    height: 28px;
    line-height: 48px;
    background-color: #FFF;
    color: #303133;
    cursor: pointer;
    border-bottom: 1px solid #EBEEF5;
    font-size: 10px;
    font-weight: 500;
    transition: border-bottom-color .3s;
    outline: 0;
}
.da-div{
    height: 500px;
    margin: 0 0 20px 10px;
    /* background-color: white; */
}
.da-div p{
    margin-top: 10px;
    padding-bottom: 5px;
    border-bottom: 0.5px darkgray solid;
    font-size: 12px;
    font-weight: 300;
}
.p1{
  background-color: rgba(242, 242, 242, 1);
  padding: 5px 0;
  font-size: 8px;
  font-weight: 300;
}
.dd1 i{
  margin-left: 10px;
}
.dd2 i{
  margin-left: 10px;
}
.dd3 i{
  margin-left: 10px;
}
.dd4 i{
  margin-left: 10px;
}
.dd4 div{
  width: 49%;
  margin-top: 20px;
  display: inline-block;
  /* height: 300px; */
  font-size: 10px;
}
.dd4 div:nth-of-type(1){
  border-right: 1px darkgray solid;
}
.dd5 i{
  margin-left: 10px;
}
.kk1 p{
  width: 50%;
  margin-left: 50px;
   
 
  margin-top: 10px;
}
.spa1{
  width: 50px;
  display: inline-block;
  font-size: 10px;
  font-weight: 300;
}
.spa2{
  width: 100px;
  display: inline-block;
  font-size: 9px;
  padding-bottom: 5px;
  border-bottom: 0.5px darkblue solid;
  font-weight: 300;
  width: 200px;
}
.butt{
  background-color: #5ba4e8;
  border-radius: 5px;
  padding: 5px 15px;
  font-size: 10px;
  color: white;
  margin-left:200px;
  margin-top: 20px;
  
}
.p11 span{
  font-size: 8px;
  font-weight: 300;
}
.p11{
  width: 95%;
  margin-top: 15px;
  padding-bottom: 10px;
  border-bottom: 0.5px darkblue solid;
}
.p12{
  width: 95%;
  margin-top: 15px;
  padding-bottom: 30px;
}
.p12 span{
  font-size: 8px;
  font-weight: 300;
}
.p13{
  width: 95%;
  
  padding-bottom: 30px;
}
.p13 span{
  font-size: 8px;
  font-weight: 300;
}
select{
  padding: 0  10px;
  margin-top: 2px;
  
}
.sp3{
  border-right: 5px;
  color: white;
  padding: 4px 10px;
  background-color: aquamarine;
}
</style>